---
title: Regsvcs.exe (Herramienta de instalación de servicios de .NET)
description: Use Regsvcs.exe, la Herramienta de instalación de servicios de .NET. Cargue y registre un ensamblado, configure los servicios agregados mediante programación a una clase, etc.
ms.date: 03/30/2017
helpviewer_keywords:
- Regsvcs.exe
- .NET Services Installation tool
- loading assemblies
- assemblies [.NET Framework], registering
- type libraries
- registering assemblies
ms.assetid: 5220fe58-5aaf-4e8e-8bc3-b78c63025804
ms.openlocfilehash: a989ddf8b14806879917e4078f60486f225b00e3
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102259208"
---
# <a name="regsvcsexe-net-services-installation-tool"></a>Regsvcs.exe (Herramienta de instalación de servicios de .NET)

La herramienta Instalación de servicios de .NET realiza las siguientes acciones:  
  
- Carga y registra un ensamblado.  
  
- Genera, registra e instala una biblioteca de tipos en una aplicación COM+ específica.  
  
- Configura los servicios que se han agregado a la clase mediante programación.  
  
 Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
      regsvcs [/c | /fc | /u] [/tlb:typeLibraryFile] [/extlb]  
[/reconfig] [/componly] [/appname:applicationName]  
[/nologo] [/quiet]assemblyFile.dll
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento|Descripción|  
|--------------|-----------------|  
|*assemblyFile.dll*|Archivo de ensamblado de origen con el que se va a trabajar. El ensamblado debe estar firmado con un nombre seguro. Para obtener más información, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md).|  
  
|Opción|Descripción|  
|------------|-----------------|  
|**/appdir:** *path*|Especifica el directorio raíz de la aplicación.|  
|**/appname:** *applicationName*|Especifica el nombre de la aplicación COM+ que se busca o se crea.|  
|**/c**|Crea la aplicación de destino.|  
|**/componly**|Solo configura componentes; no tiene en cuenta métodos o interfaces.|  
|**/exapp**|Indica a la herramienta que debe contar con una aplicación existente.|  
|**/extlb**|Utiliza una biblioteca de tipos existente.|  
|**/fc**|Busca o crea la aplicación de destino.|  
|**/help**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
|**/noreconfig**|No vuelve a configurar una aplicación de destino existente.|  
|**/nologo**|Suprime la presentación de la portada de inicio de Microsoft.|  
|**/parname:** *name*|Especifica el nombre o el identificador de la aplicación COM+ que se busca o se crea.|  
|**/reconfig**|Vuelve a configurar una aplicación de destino existente. Este es el valor predeterminado.|  
|**/tlb:** *typelibraryfile*|Especifica el archivo de biblioteca de tipos que se instala.|  
|**/u**|Desinstala la aplicación de destino.|  
|**/quiet**|Especifica el modo silencioso; suprime el logotipo y la presentación de mensajes de operaciones correctas.|  
|**/?**|Muestra las opciones y la sintaxis de los comandos para la herramienta.|  
  
## <a name="remarks"></a>Comentarios  

 Regsvcs.exe requiere un archivo de ensamblado de origen especificado por *assemblyFile.dll*. Este ensamblado debe estar firmado con un nombre seguro. Para obtener más información sobre la firma con nombres seguros, vea [Procedimiento para firmar un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md). Los nombres de la aplicación de destino y del archivo de biblioteca de tipos son opcionales. El argumento *applicationName* se puede generar a partir del archivo de ensamblado de origen, y Regsvcs.exe lo creará si no existe todavía. El argumento *typelibraryfile* puede especificar un nombre de biblioteca de tipos. Si no se especifica ningún nombre de biblioteca de tipos, Regsvcs.exe utiliza el nombre del ensamblado como valor predeterminado.  
  
 Cuando Regsvcs.exe registra los métodos de un componente, se le aplican las [peticiones](/previous-versions/dotnet/netframework-4.0/9kc0c6st(v=vs.100)) y las [peticiones de vínculos](../misc/link-demands.md) de estos métodos. Como la herramienta se ejecuta en un entorno de confianza total, la mayoría de las peticiones de permisos se llevan a cabo satisfactoriamente. Sin embargo, Regsvcs.exe no puede registrar componentes con métodos protegidos por una petición o una petición de vínculo para <xref:System.Security.Permissions.StrongNameIdentityPermission> o <xref:System.Security.Permissions.PublisherIdentityPermission>.  
  
 Debe tener privilegios administrativos en el equipo local para utilizar Regsvcs.exe.  
  
 Si Regsvcs.exe genera un error durante la realización de alguna de estas acciones, muestra los mensajes de error correspondientes.  
  
## <a name="examples"></a>Ejemplos  

 El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `myTest.tlb`.  
  
```console  
regsvcs /appname:myTargetApp myTest.dll  
```  
  
 El comando siguiente agrega todas las clases públicas incluidas en `myTest.dll` a `myTargetApp` (aplicación COM+ existente) y genera la biblioteca de tipos `newTest.tlb`.  
  
```console  
regsvcs /appname:myTargetApp /tlb:newTest.tlb myTest.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Herramientas](index.md)
- [Cómo: Firma de un ensamblado con un nombre seguro](../../standard/assembly/sign-strong-name.md)
- [Shells de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell)
