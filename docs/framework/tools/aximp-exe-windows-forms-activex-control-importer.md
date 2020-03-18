---
title: Aximp.exe (Importador de controles ActiveX de Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls, hosting in Windows Forms
- ActiveX Control Importer
- type definitions, converting
- Aximp.exe
- Windows Forms ActiveX Control Importer
ms.assetid: 482c0d83-7144-4497-b626-87d2351b78d0
ms.openlocfilehash: 6d58d1df81780c3033eab7c1ac3e860adeb374b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180426"
---
# <a name="aximpexe-windows-forms-activex-control-importer"></a>Aximp.exe (Importador de controles ActiveX de Windows Forms)
El Importador de controles ActiveX convierte definiciones de tipos de una biblioteca de tipos COM para un control ActiveX en un control de Windows Forms.  
  
 Windows Forms solo puede hospedar controles de Windows Forms; es decir, clases derivadas de <xref:System.Windows.Forms.Control>. Aximp.exe genera una clase contenedora para un control ActiveX que se puede hospedar en un Windows Form. Esto permite utilizar la misma compatibilidad en tiempo de diseño y la misma metodología de programación que si se tratase de controles usuales de Windows Forms.  
  
 Para hospedar el control ActiveX, debe generar un control contenedor que se derive de <xref:System.Windows.Forms.AxHost>. Este control contenedor contiene una instancia del control ActiveX subyacente. También sabe cómo establecer comunicación con el control ActiveX, pero aparece como un control de Windows Forms. Este control generado contiene el control ActiveX y proporciona sus propiedades, métodos y eventos como si fuesen propios.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
aximp [options]{file.dll | file.ocx}  
```  
  
## <a name="remarks"></a>Comentarios  
  
|Argumento|Description|  
|--------------|-----------------|  
|*file*|Nombre del archivo de código fuente que contiene el control ActiveX que se va a convertir. Este argumento debe tener la extensión .ocx o .dll.|  
  
|Opción|Description|  
|------------|-----------------|  
|`/delaysign`|Especifica que Aximp.exe debe firmar el control resultante mediante la opción de firma retardada. Debe especificar esta opción con la opción `/keycontainer:`, `/keyfile:` o `/publickey:`. Para obtener más información sobre el proceso de firma retardada, vea [Retrasar la firma de un ensamblado](../../standard/assembly/delay-sign.md).|  
|`/help`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|`/keycontainer:` *nombreContenedor*|Firma el control resultante con un nombre seguro mediante el par de claves pública y privada que se encuentra en el contenedor de claves especificado mediante *containerName*.|  
|`/keyfile:` *nombre de archivo*|Firma el control resultante con un nombre seguro mediante el par de claves pública y privada oficial del editor que se encuentra en *filename*.|  
|`/nologo`|Suprime la presentación de la portada de inicio de Microsoft.|  
|`/out:` *nombre de archivo*|Especifica el nombre del ensamblado que se va a crear.|  
|`/publickey:` *nombre de archivo*|Firma el control resultante con un nombre seguro mediante la clave pública que se encuentra en el archivo especificado por *filename*.|  
|`/rcw:` *nombre de archivo*|Utiliza el contenedor invocable en tiempo de ejecución especificado en lugar de generar uno nuevo. Puede especificar varias instancias. El directorio actual se utiliza para las rutas de acceso relativas. Para más información, vea [Ccontenedor RCW](../../standard/native-interop/runtime-callable-wrapper.md).|  
|`/silent`|Suprime la presentación de mensajes de aprobación.|  
|`/source`|Genera código fuente de C# para el contenedor de Windows Forms.|  
|`/verbose`|Especifica el modo detallado; muestra información adicional del progreso.|  
|`/?`|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
 Aximp.exe convierte una biblioteca de tipos completa de controles ActiveX de una vez y produce un conjunto de ensamblados que contienen los metadatos de Common Language Runtime y la implementación de controles para los tipos definidos en la biblioteca de tipos original. Los archivos generados se nombran conforme al siguiente patrón:  
  
 Proxy de Common Language Runtime para tipos COM: *progid*.dll  
  
 Proxy de Windows Forms para controles ActiveX (donde Ax significa ActiveX): Ax*progid*.dll  
  
> [!NOTE]
> Si el nombre de un miembro del control ActiveX coincide con un nombre definido en .NET Framework, Aximp.exe agregará el prefijo "Ctl" al nombre del miembro al crear la clase derivada AxHost. Por ejemplo, si el control ActiveX tiene un miembro denominado "Layout", el nombre de este se cambia a "CtlLayout" en la clase derivada AxHost porque el evento Layout está definido en .NET Framework.  
  
 Puede examinar estos archivos generados con herramientas como [Ildasm.exe (Desensamblador de IL)](ildasm-exe-il-disassembler.md).  
  
 No se puede utilizar Aximp.exe con el fin de generar un ensamblado .NET para el control ActiveX WebBrowser (shdocvw.dll).  
  
 Cuando se ejecuta Aximp.exe sobre shdocvw.dll, siempre se crea otro archivo denominado shdocvw.dll en el directorio desde el que se ejecuta la herramienta. Si este archivo generado se ubica en el directorio Documents and Settings, causará problemas a Microsoft Internet Explorer y al Explorador de Windows. Cuando se reinicia el equipo, Windows busca una copia de shdocvw.dll en el directorio los Documents and Settings antes que en el directorio system32. Usará la copia que encuentre en Documents and Settings e intentará cargar los contenedores administrados. Internet Explorer y el Explorador de Windows no funcionarán correctamente, porque se basan en el motor de representación de la versión de shdocvw.dll ubicada en el directorio system32. Si se produce este problema, elimine la copia de shdocvw.dll del directorio Documents and Settings y reinicie el equipo.  
  
 Si se utiliza Aximp.exe con shdocvw.dll con el fin de crear un ensamblado .NET para utilizarlo en el desarrollo de aplicaciones, también pueden producirse problemas. En este caso, la aplicación cargará la versión del sistema de shdocvw.dll y la versión generada, por lo que la versión del sistema podría tener prioridad. En este caso, al intentar cargar una página web dentro del control ActiveX WebBrowser, es posible que a los usuarios les aparezca un cuadro de diálogo para abrir o guardar. Cuando el usuario haga clic en **Abrir**, la página web se abrirá en Internet Explorer. Esto solo ocurre en los equipos que ejecutan Internet Explorer versión 6 o una versión anterior. Para evitar este problema, use el control <xref:System.Windows.Forms.WebBrowser> administrado o Visual Studio para generar el control shdocvw.dll administrado, como se describe en [Cómo: Agregar referencias a bibliotecas de tipos](../interop/how-to-add-references-to-type-libraries.md).  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente genera los archivos MediaPlayer.dll y AxMediaPlayer.dll para el control de Media Player `msdxm.ocx`.  
  
```console
aximp c:\systemroot\system32\msdxm.ocx  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Ildasm.exe (Desensamblador de IL)](ildasm-exe-il-disassembler.md)
