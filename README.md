## *Numerous checkpoints*
Библиотека позволяет показать многочисленное количество чекпоинтов для игрока.

## *Установка*
- Переместите файл numerous_cp в папку с инклудами игрового мода.
```pawn
#include <numerous_cp>
```

## *Использование*
```pawn
cmd:createncp(playerid)
{
	new Float: x, Float: y, Float: z;
	GetPlayerPos(playerid, x, y, z);

	ncp_PlayerCreate(playerid, x, y, z);

	return true;
}

cmd:destroyncp(playerid, params[])
{
	new id;
    if (sscanf(params, "d", id)) {
        return SendClientMessage(playerid, -1, "/destroyncp [ID]");
	}

	ncp_PlayerDestroy(playerid, id);

	return true;
}
```

## *Функции*

## *Коллбэки*