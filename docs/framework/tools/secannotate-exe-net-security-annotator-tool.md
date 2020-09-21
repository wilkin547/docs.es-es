---
title: SecAnnotate.exe (Herramienta Anotador de seguridad de .NET)
description: Use SecAnnotate.exe, la herramienta Anotador de seguridad de .NET. Identifique las partes SecurityCritical y SecuritySafeCritical de uno o más ensamblados.
ms.date: 03/30/2017
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
ms.openlocfilehash: 408a3064b67cae2d75c80881f918c774e05866e6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558386"
---
# <a name="secannotateexe-net-security-annotator-tool"></a>SecAnnotate.exe (Herramienta Anotador de seguridad de .NET)
La herramienta Anotador de seguridad de .NET (SecAnnotate.exe) es una aplicación de línea de comandos que identifica los elementos `SecurityCritical` y `SecuritySafeCritical` de uno o más ensamblados.  
  
 El [Anotador de seguridad](https://marketplace.visualstudio.com/items?itemName=sheldonb.SecurityAnnotator), que es una extensión de Visual Studio, proporciona una interfaz gráfica de usuario a SecAnnotate.exe y permite ejecutar la herramienta desde Visual Studio.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente (los valores de *parameters* se describen en la sección siguiente y *assemblies* se compone de uno o varios nombres de ensamblado separados por espacios en blanco):  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Opción|Descripción|  
|------------|-----------------|  
|`/a`<br /><br /> o<br /><br /> `/showstatistics`|Muestra estadísticas sobre el uso de transparencia en los ensamblados que se van a analizar.|  
|`/d:` *directory*<br /><br /> o<br /><br /> `/referencedir:` *directory*|Especifica el directorio en el que buscar los ensamblados dependientes durante la anotación.|  
|`/i`<br /><br /> o<br /><br /> `/includesignatures`|Incluye información de signatura ampliada en el archivo de informe de anotación.|  
|`/n`<br /><br /> o<br /><br /> `/nogac`|Suprime la búsqueda de los ensamblados a los que se hace referencia en la caché global de ensamblados.|  
|`/o:` *output.xml*<br /><br /> o<br /><br /> `/out:` *output.xml*|Especifica el archivo de anotación de salida.|  
|`/p:` *maxpasses*<br /><br /> o<br /><br /> `/maximumpasses:` *maxpasses*|Especifica el número máximo de pasos de anotación que se realizan en los ensamblados antes de detener la generación de nuevas anotaciones.|  
|`/q`<br /><br /> o<br /><br /> `/quiet`|Especifica el modo silencioso, en el que el anotador no genera mensajes de salida de estado; solo genera información de error.|  
|`/r:` *assembly*<br /><br /> o<br /><br /> `/referenceassembly:` *assembly*|Incluye el ensamblado especificado al resolver ensamblados dependientes durante la anotación. Los ensamblados de referencia tienen prioridad sobre los ensamblados que se encuentran en la ruta de acceso de referencia.|  
|`/s:` *rulename*<br /><br /> o<br /><br /> `/suppressrule:` *rulename*|Suprime la ejecución de la regla de transparencia especificada en los ensamblados de entrada.|  
|`/t`<br /><br /> o<br /><br /> `/forcetransparent`|Fuerza a la herramienta Anotador a tratar todos los ensamblados que no tienen ninguna anotación de transparencia como si fueran completamente transparentes.|  
|`/t`:*assembly*<br /><br /> o<br /><br /> `/forcetransparent`:*assembly*|Fuerza al ensamblado proporcionado a que sea transparente, independientemente de las anotaciones de nivel de ensamblado actuales.|  
|||  
|`/v`<br /><br /> o<br /><br /> `/verify`|Comprueba únicamente que las anotaciones de un ensamblado sean correctas, pero no intenta ejecutar varios pasos para buscar todas las anotaciones necesarias si el ensamblado no supera la comprobación.|  
|`/x`<br /><br /> o<br /><br /> `/verbose`|Especifica resultados detallados al anotar.|  
|`/y:` *directory*<br /><br /> o<br /><br /> `/symbolpath:` *directory*|Incluye el directorio especificado al buscar archivos de símbolos durante la anotación.|  
  
## <a name="remarks"></a>Comentarios  
 Los parámetros y ensamblados también se pueden proporcionar en un archivo de respuesta que se especifica en la línea de comandos y lleva el prefijo de una arroba (@). Cada línea del archivo de respuesta debe contener un nombre de ensamblado o parámetro único.  
  
 Para obtener más información sobre el Anotador de seguridad de .NET, vea la entrada sobre [cómo usar SecAnnotate para analizar los ensamblados y detectar infracciones de transparencia](/archive/blogs/shawnfa/using-secannotate-to-analyze-your-assemblies-for-transparency-violations-an-example) en el blog de seguridad de .NET.  
  
## <a name="examples"></a>Ejemplos
