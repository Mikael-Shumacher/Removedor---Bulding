#define Removi "RemoveMap.ini"//coloque no topo da GM abaixo das includes 

CMD:removerobj(playerid, const params[])//caso esteja dando algum erro estranho retire o "const"
{
    new Strv[200], bot[200], String[200];
    new obj, Float:esp, Float:oX, Float:oY, Float:oZ;
    GetPlayerPos(playerid, oX, oY, oZ); 
    if(sscanf(params, "df", obj, esp)) return SendClientMessage(playerid , 0xFFFF00AA, "Use: /removerobj [ID Objeto] [Raio] [Comentario]");
    RemoveBuildingForPlayer(playerid, obj, oX, oY, oZ, esp);
    format(String, sizeof(String), "{0000FF}Voce removeu o objeto {00FF00}[%d]{0000FF} do mapa", obj);
    SendClientMessage(playerid, 0x0000FFAA, String);
    if(!DOF2_FileExists(Removi))
    {
        DOF2_CreateFile(Removi);
    }
    format(Strv, sizeof(Strv), "RemoveBuildingForPlayer(playerid, %d, %f, %f, %f, %f);", obj, oX, oY, oZ, esp);
    DOF2_SetString(Removi, Strv, params);
    DOF2_SetString(Removi, "=======================================================", bot);
    DOF2_SaveFile();
    return 1;
}
