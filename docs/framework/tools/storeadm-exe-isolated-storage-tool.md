---
title: Storeadm.exe (herramienta de almacenamiento aislado)
description: Lea acerca de Storeadm.exe, la Herramienta de almacenamiento aislado. Esta herramienta enumera o quita todos los almacenes existentes del usuario actual.
ms.date: 03/30/2017
helpviewer_keywords:
- Storeadm.exe
- listing stores for current user
- Isolated Storage tool
- stores, current user
- removing stores
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
ms.openlocfilehash: e6c2fc15ba2b6fef27bb57344628638a99103916
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258743"
---
# <a name="storeadmexe-isolated-storage-tool"></a>Storeadm.exe (herramienta de almacenamiento aislado)

La herramienta de almacenamiento aislado incluye o quita todos los almacenes existentes del usuario actual.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/h**[**elp**]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/list**|Muestra todos los almacenes existentes del usuario actual. Entre estos se incluyen los almacenes de todas las aplicaciones o ensamblados ejecutados por este usuario.|  
|**/machine**|Selecciona el almacén del equipo. Use esta opción con las opciones **/list** o **/remove** para especificar que la acción se debe aplicar al almacén del equipo.<br /><br /> Se trata de una novedad de la versión 2.0 de .NET Framework|  
|**/quiet**|Especifica el modo silencioso; suprime los resultados que contienen información mostrándose únicamente mensajes de error.|  
|**/remove**|Quita de forma permanente todos los almacenes existentes del usuario actual.|  
|**/roaming**|Selecciona el almacén móvil. Use esta opción con las opciones **/list** o **/remove** para especificar que la acción se debe aplicar al almacén móvil.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  

 La ejecución de Storeadm.exe desde la línea de comandos sin especificar ninguna opción muestra la sintaxis y las opciones para la herramienta.  
  
 Las opciones **/list** y **/remove** se usan normalmente de una en una, pero si se especifican dos o más opciones, se ejecutarán en el orden en que aparezcan en la línea de comandos.  
  
 Las aplicaciones tienen la opción de guardar los datos en uno de los dos siguientes almacenes de usuario o en el almacén del equipo:  
  
- El almacén local, que está situado en una ubicación donde se anula la posibilidad de movilidad (en Windows 2000 y posterior), aunque la movilidad de datos de usuario esté habilitada para el usuario.  
  
- El almacén móvil, que se encuentra en una ubicación con posibilidad de movilidad, pero esta acción solo es posible si la movilidad está habilitada para el usuario mediante la administración de Windows NT.  
  
- El almacén del equipo, que es común a todos los usuarios del equipo y se almacena bajo un directorio común en dicho equipo.  
  
    > [!NOTE]
    > El almacén del equipo es una novedad de la versión 2.0 de .NET Framework.  
  
 Si la movilidad está habilitada realmente para el usuario, no afecta a la administración de Storeadm.exe. Si la herramienta se ejecuta sin ninguna opción, todas las acciones se aplican al almacén local. Si la herramienta se ejecuta con la opción **/roaming**, todas las acciones se aplican al almacén que tiene posibilidad de movilidad. Si la herramienta se ejecuta con la opción **/machine**, todas las acciones se aplican al almacén del equipo.  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Almacenamiento aislado](../../standard/io/isolated-storage.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
