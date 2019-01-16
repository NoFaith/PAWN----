#include <a_samp>
#include <sscanf>
#include <zcmd>
#include <dini>
// feel free to edit this FS as you want, but dont remove the credits !! <3
#define    COLOR_ERROR                0xFF0000AA
#define COLOR_YELLOW           0xFFFF00AA
#define 		green 					0x33FF33AA
/*
M A D E   B Y    wuzue, you can find me on Skype: renan.araujo279 or mail me: burzuned@gmail.com
github.com/wuzue
*/
public OnFilterScriptInit()
{
    print("\n********************************************");
    print("SIMPLE AUDIO STREAM FOR SAMP - made by wuzue ");
    print("**********************************************\n");
    return 1;
}

CMD:playsong(playerid, params[])//command to start playing the song
{
    //new adminname[49];
    if(isnull(params)) return SendClientMessage(playerid, COLOR_ERROR, "[ XxX ] CMD: /playsong [URL]");
    for(new u; u < MAX_PLAYERS; u++)
    {
        PlayAudioStreamForPlayer(u, params);
    }
    SendClientMessageToAll(COLOR_YELLOW, "An admin put a song, to stop, type: /stopsong");
    return 1;
}
//It would look better if I put a box to type the CMD to play the song....but i wanted to make it simple.

CMD:stopsong(playerid, params[])
{
    StopAudioStreamForPlayer(playerid);//Some people told me that sometimes it doesnt close in the first try
    SendClientMessage( playerid, COLOR_YELLOW, "[ XxX ] You stopped the current song");//but ill look to fix it
    return 1;
}

CMD:ssongtoall(playerid, params[])
{
    new adminname[24], string[128];
    GetPlayerName(playerid, adminname, 24);

    if(!IsPlayerAdmin(playerid)) return SendClientMessage(playerid, COLOR_ERROR, "[ XxX ] You are not allowed");
    for( new u; u < MAX_PLAYERS; u++ )
    {
    StopAudioStreamForPlayer( u );
    }
    format(string,sizeof(string),"[ > ] The admin %s stopped the song", adminname );
    SendClientMessage(playerid, COLOR_YELLOW, string);
    return 1;
}

CMD:clearchat(playerid, params[])
{
	if(PlayerInfo[playerid][Level] < 1)
	    return SendClientMessage(playerid,red,"ERROR: You are not allowed to use this command");

	CMDMessageToAdmins(playerid, "CLEARCHAT");
	for(new i = 0; i < 100; i++) SendClientMessageToAll(green," ");
	return 1;
