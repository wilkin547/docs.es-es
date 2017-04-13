---
title: "Storeadm.exe (Isolated Storage Tool) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Storeadm.exe"
  - "listing stores for current user"
  - "Isolated Storage tool"
  - "stores, current user"
  - "removing stores"
ms.assetid: b81202b8-d91d-4b23-9c53-4a112f74a44a
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Storeadm.exe (Isolated Storage Tool)
La herramienta de almacenamiento aislado incluye o quita todos los almacenes existentes del usuario actual.  
  
 Esta herramienta se instala automáticamente con Visual Studio.  Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores \(o el Símbolo del sistema de Visual Studio en Windows 7\).  Para obtener más información, vea [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## Sintaxis  
  
```  
  
storeadm [/list][/machine][/remove][/roaming][/quiet]  
```  
  
#### Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|**\/h**\[**elp**\]|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**\/list**|Muestra todos los almacenes existentes del usuario actual.  Entre estos se incluyen los almacenes de todas las aplicaciones o ensamblados ejecutados por este usuario.|  
|**\/machine**|Selecciona el almacén del equipo.  Utilice esta opción junto con la opción **\/list** o **\/remove** para especificar que la acción debe aplicarse al almacén del equipo.<br /><br /> Se trata de una novedad de la versión 2.0 de .NET Framework|  
|**\/quiet**|Especifica el modo silencioso; suprime los resultados que contienen información mostrándose únicamente mensajes de error.|  
|**\/remove**|Quita de forma permanente todos los almacenes existentes del usuario actual.|  
|**\/roaming**|Selecciona el almacén móvil.  Utilice esta opción con las opciones **\/list** o **\/remove** para especificar que la acción se debe aplicar al almacén móvil.|  
|**\/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## Comentarios  
 La ejecución de Storeadm.exe desde la línea de comandos sin especificar ninguna opción muestra la sintaxis y las opciones para la herramienta.  
  
 Las opciones **\/list** y **\/remove** se utilizan normalmente de una en una; sin embargo, si se especifican dos o más opciones, se ejecutarán en el orden en que aparezcan en la línea de comandos.  
  
 Las aplicaciones tienen la opción de guardar los datos en uno de los dos siguientes almacenes de usuario o en el almacén del equipo:  
  
-   El almacén local, que está situado en una ubicación donde se anula la posibilidad de movilidad \(en Windows 2000 y posterior\), aunque la movilidad de datos de usuario esté habilitada para el usuario.  
  
-   El almacén móvil, que se encuentra en una ubicación con posibilidad de movilidad, pero esta acción solo es posible si la movilidad está habilitada para el usuario mediante la administración de Windows NT.  
  
-   El almacén del equipo, que es común a todos los usuarios del equipo y se almacena bajo un directorio común en dicho equipo.  
  
    > [!NOTE]
    >  El almacén del equipo es una novedad de la versión 2.0 de .NET Framework.  
  
 Si la movilidad está habilitada realmente para el usuario, no afecta a la administración de Storeadm.exe.  Si la herramienta se ejecuta sin ninguna opción, todas las acciones se aplican al almacén local.  Si la herramienta se ejecuta con la opción **\/roaming**, todas las acciones se aplican al almacén que tiene posibilidad de movilidad.  Si la herramienta se ejecuta con la opción **\/machine**, todas las acciones se aplican al almacén del equipo.  
  
## Vea también  
 [Tools](../../../docs/framework/tools/index.md)   
 [Almacenamiento aislado](../../../docs/standard/io/isolated-storage.md)   
 [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md)