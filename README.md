## *Numerous checkpoints*
Библиотека позволяет показать многочисленное количество чекпоинтов для игрока.
<img src="https://imgur.com/ViATHuD.png">

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

### ncp_PlayerCreate(playerid, Float: x, Float: y, Float: z)
> Создаёт новый чекпоинт.
> * `playerid` - ID игрока.
> * `x` - координата X.
> * `y` - координата Y.
> * `z` - координата Z.

### ncp_PlayerDestroy(playerid, ncp_id)
> Уничтожает чекпоинт.
> * `playerid` - ID игрока.
> * `ncpid` - ID чекпоинта.

### ncp_IsPlayerEntered(playerid, ncp_id)
> Вошёл ли игрок в зону действия чекпоинта.
> * `playerid` - ID игрока.
> * `ncpid` - ID чекпоинта.

### ncp_IsValid(ncp_id)
> Валиден ли чекпоинт.
> * `ncpid` - ID чекпоинта.

## *Коллбэки*

### public OnPlayerEnterNCP(playerid, ncpid)
> Вызывается когда игрок вошёл в зону действия чекпоинта.
> * `playerid` - ID игрока.
> * `ncpid` - ID чекпоинта.

### public OnPlayerLeaveNCP(playerid, ncpid)
> Вызывается когда игрок покинул зону действия чекпоинта.
> * `playerid` - ID игрока.
> * `ncpid` - ID чекпоинта.