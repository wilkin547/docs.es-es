---
title: "Soluci&#243;n de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, solución de problemas en instalaciones bloqueadas"
  - "instalaciones bloqueadas de .NET Framework, solucionar problemas"
ms.assetid: c3fdfbc1-ed99-4202-a2b0-8c4f1646385d
caps.latest.revision: 57
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 39
---
# Soluci&#243;n de problemas en instalaciones y desinstalaciones bloqueadas de .NET Framework
Al ejecutar el [instalador web o sin conexión](../../../docs/framework/install/guide-for-developers.md) de .NET Framework 4.5, 4.5.1, 4.5.2, 4.6 o 4.6.1, puede producirse algún problema que impida o bloquee la instalación de .NET Framework. En la tabla siguiente se enumeran los posibles problemas de bloqueo y se incluyen vínculos a información sobre solución de problemas.  
  
 En esta tabla, 4.5.*x* hace referencia a .NET Framework 4.5 y a sus versiones secundarias, 4.5.1 y 4.5.2, 4.6 o 4.6.1.  
  
|Mensaje de bloqueo|Para obtener más información o para resolver el problema|  
|------------------------|--------------------------------------------------------------|  
|Si se desinstala Microsoft .NET Framework, puede dar lugar a que otras aplicaciones dejen de funcionar.|En general, no debe desinstalar ninguna versión de .NET Framework que esté instalada en el equipo, ya que puede haber aplicaciones que dependan de una versión concreta de .NET Framework. Para obtener más información, consulte [.NET Framework para usuarios](../../../docs/framework/get-started/index.md#ForUsers) en la *Guía de introducción*.|  
|.NET Framework 4.5*.x*\/4.6*.x* \(*idioma*\) requiere .NET Framework 4.5*.x*\/4.6*.x*. Instale .NET Framework 4.5*.x*\/4.6*.x* desde el Centro de descarga y vuelva a ejecutar el programa de instalación.|Debe instalar la versión en inglés de la versión especificada de .NET Framework antes de instalar un paquete de idioma. Para obtener más información, consulte la sección sobre [Para instalar paquetes de idioma](../../../docs/framework/install/guide-for-developers.md#standalone_language_packs) en la guía de instalación.|  
|No se puede instalar .NET Framework 4.5*.x*\/4.6*.x*. Otras aplicaciones del equipo no son compatibles con este programa.<br /><br /> O bien<br /><br /> Otras aplicaciones del equipo no son compatibles con este programa.|La causa más probable de este mensaje es que se instaló una versión Preview o RC de .NET Framework. Desinstale la versión Preview o RC y vuelva a ejecutar el programa de instalación.|  
|.NET Framework 4.5*.x*\/4.6*.x* no se puede desinstalar con este paquete. Para desinstalar .NET Framework 4.5*.x*\/4.6*.x* en el equipo, vaya al **Panel de control**, elija **Programas y características**, escoja **Ver actualizaciones instaladas**, seleccione Actualización para Microsoft Windows \(KB2828152\) y, por último, elija **Desinstalar**.|El paquete que está instalando no desinstala la versión Preview o RC de .NET Framework.<br /><br /> Desinstale la versión Preview o RC desde el Panel de control.|  
|No se puede desinstalar .NET Framework 4.5*.x*\/4.6*.x*. Otras aplicaciones del equipo dependen de este programa.|En general, no debe desinstalar ninguna versión de .NET Framework que esté instalada en el equipo, ya que puede haber aplicaciones que dependan de una versión concreta de .NET Framework. Para obtener más información, consulte [.NET Framework para usuarios](../../../docs/framework/get-started/index.md#ForUsers) en la *Guía de introducción*.|  
|El paquete redistribuible de .NET Framework 4.5*.x*\/4.6*.x* no es válido para este sistema operativo. Descargue .NET Framework 4.5*.x*\/4.6*.x* para su sistema operativo desde el Centro de descarga de Microsoft.|Es posible que esté intentando instalar [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6 o 4.6.1 en una plataforma no compatible o que haya elegido un paquete de instalación que no incluye los componentes de todos los sistemas operativos compatibles. Ejecute de nuevo la instalación mediante el instalador sin conexión \(para las versiones [4.5.1](http://go.microsoft.com/fwlink/p/?LinkId=309493), [4.5.2](http://go.microsoft.com/fwlink/p/?LinkId=397706), [4.6](http://go.microsoft.com/fwlink/p/?LinkId=528233) o [4.6.1](http://go.microsoft.com/fwlink/p/?LinkId=671744)\). Para obtener más información, consulte la [guía de instalación](../../../docs/framework/install/guide-for-developers.md) y los [requisitos del sistema](../../../docs/framework/get-started/system-requirements.md) para los sistemas operativos compatibles.|  
|El equipo está ejecutando actualmente una instalación Server Core del sistema operativo Windows Server 2008. .NET Framework 4.5.*x* requiere una versión posterior del sistema operativo. Instale Windows Server 2008 R2 SP1 o posterior y vuelva a ejecutar el programa de instalación de .NET Framework 4.5.*x*.|[!INCLUDE[net_v451](../../../includes/net-v451-md.md)] y 4.5.2 son compatibles con el rol Server Core con Windows Server 2008 R2 SP1 o versiones posteriores. Vea [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md).|  
|No tiene privilegios suficientes para completar esta operación para todos los usuarios de este equipo. Inicie sesión como administrador y ejecute de nuevo el **programa de instalación**.|Tiene que ser administrador del equipo para instalar .NET Framework.|  
|El programa de instalación no puede continuar porque una instalación anterior requiere reiniciar el equipo. Reinicie el equipo y ejecute de nuevo el programa de instalación.|Siempre es necesario reiniciar para completar una instalación. Siga las instrucciones para reiniciar el equipo y vuelva a ejecutar el programa de instalación.|  
|Ya se ha instalado en el equipo .NET Framework 4.5*.x*\/4.6*.x* \(ESN\) o una actualización posterior.|No se requiere ninguna acción.|  
|El programa de instalación de .NET Framework no se puede ejecutar en modo de compatibilidad de programas.|Vea la sección [Problemas de compatibilidad de programas](#compat) más adelante en este artículo.|  
|No se instaló .NET framework 4.5*.x*\/4.6*.x*, debido a que el almacén de componentes está dañado.|Consulte el artículo [Corregir errores de corrupción de Windows con la herramienta DISM o System Update Readiness](https://support.microsoft.com/en-us/kb/947821) para obtener más información.|  
|El programa de instalación no se puede ejecutar porque el servicio Windows Installer no está disponible en este equipo.|Consulte la información acerca del [Error del servicio de Windows Installer al instalar o actualizar programas](http://go.microsoft.com/fwlink/p/?LinkId=248684) en el sitio web del soporte técnico de Microsoft.|  
|Puede que el programa de instalación no se ejecute correctamente porque el servicio Windows Update no está disponible en este equipo.|El equipo se puede configurar para que utilice Windows Server Update Services \(WSUS\) en lugar de Microsoft Windows Update. Para obtener más información, consulte la sección del código de error 0x800F0906 en el artículo [Códigos de error al intentar instalar .NET Framework 3.5 en Windows 8 o en Windows Server 2012](http://support.microsoft.com/kb/2734782).<br /><br /> Consulte también [Cómo obtener la última versión del Agente de Windows Update para ayudarle a administrar las actualizaciones de un equipo](http://go.microsoft.com/fwlink/p/?LinkId=248437) en el sitio web del soporte técnico de Microsoft.|  
|Puede que el programa de instalación no se ejecute correctamente porque el Servicio de transferencia inteligente en segundo plano \(BITS\) no está disponible en este equipo.|Consulte el artículo [Actualizar para impedir un bloqueo del Servicio de transferencia inteligente en segundo plano \(BITS\) en un equipo con Windows Vista](http://go.microsoft.com/fwlink/p/?LinkId=248680), en el sitio web del soporte técnico de Microsoft.|  
|.NET Framework 4.5.*.x*\/4.6 ya forma parte de este sistema operativo. No es necesario instalar el paquete redistribuible de .NET Framework 4.5*.x*\/4.6.|No se requiere ninguna acción. Consulte en [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md) los sistemas operativos admitidos.|  
|.NET Framework 4.5*.x*\/4.6*.x* no es compatible con este sistema operativo.|Consulte en [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md) los sistemas operativos admitidos.<br /><br /> Si existen errores de instalación de .NET Framework en Windows 7, este mensaje normalmente indica que Windows 7 SP1 no está instalado. Para sistemas de Windows 7, tenga en cuenta que .NET Framework requiere Windows 7 SP1. Si usa Windows 7 y aún no ha instalado Service Pack 1, deberá hacerlo antes de instalar .NET Framework.|  
|El equipo está ejecutando actualmente una instalación Server Core del sistema operativo Windows Server 2008. .NET Framework 4.5.*x* requiere una versión completa del sistema operativo o de Server Core 2008 R2 SP1. Instale la versión completa de Windows Server 2008 SP2, Windows Server 2008 R2 SP1 o Server Core 2008 R2 SP1 y vuelva a ejecutar el programa de instalación de .NET Framework 4.5.*x*.|.NET Framework. se admite en el rol Server Core con Windows Server 2008 R2 SP1 o versiones posteriores. Vea [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md).|  
|.NET Framework 4.5.*x* ya forma ya parte de este sistema operativo, pero actualmente está desactivado \(solo [!INCLUDE[winserver8](../../../includes/winserver8-md.md)]\).|Consulte [Activar o desactivar las características de Windows](http://go.microsoft.com/fwlink/p/?LinkId=248438) en el sitio web de Windows.|  
|Este programa de instalación requiere un equipo x86. No se puede instalar en equipos x64 o IA64.|Consulta [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md) en MSDN Library.|  
|Este programa de instalación requiere un equipo x64 o x86. No se puede instalar en un equipo IA64.|Consulta [Requisitos del sistema](../../../docs/framework/get-started/system-requirements.md) en MSDN Library.|  
  
<a name="compat"></a>   
### Problemas de compatibilidad de programas  
 Al instalar .NET Framework 4.5 o una de sus versiones secundarias se produce el código de error 1603 o se bloquea cuando se ejecuta en el modo de compatibilidad de programas de Windows. El **Asistente para la compatibilidad de programas** indica que es posible que .NET Framework no se haya instalado correctamente y le solicita reinstalarlo utilizando la configuración recomendada \(modo de compatibilidad de programas\). El Asistente para la compatibilidad de programas también podría haber establecido el modo de compatibilidad después de que se produjeran intentos anteriores erróneos o cancelados para ejecutar el programa de instalación de .NET Framework.  
  
 El programa de instalación de .NET Framework no se puede ejecutar en el modo de compatibilidad de programas. Para resolver este problema de bloqueo, debe asegurarse de que la configuración del modo de compatibilidad no está habilitada en todo el sistema en el Editor del Registro:  
  
1.  Elija el botón **Iniciar** y, a continuación, **Ejecutar**.  
  
2.  En el cuadro de diálogo **Ejecutar**, escriba `regedit` y después elija **Aceptar**.  
  
3.  En el Editor del Registro, busque las subclaves siguientes:  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Compatibility Assistant\\Persisted  
  
    -   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers  
  
4.  En la columna Nombre, busque los nombres de las descargas de [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], 4.5.1, 4.5.2, 4.6 o 4.6.1, según la versión que vaya a instalar, y elimine estas entradas. Para obtener más información sobre los nombres de descarga, lea el artículo [Guía de instalación](../../../docs/framework/install/guide-for-developers.md).  
  
5.  Vuelva a ejecutar el instalador de .NET Framework para la versión 4.5, 4.5.1, 4.5.2, 4.6 o 4.6.1.  
  
## Vea también  
 [Guía de instalación](../../../docs/framework/install/guide-for-developers.md)