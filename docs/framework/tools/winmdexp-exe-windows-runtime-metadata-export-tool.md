---
title: Winmdexp.exe (Herramienta de exportación de metadatos de Windows Runtime)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
ms.openlocfilehash: 52820b78f6ed7b02e80df66f90a01143b31d9b29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74447279"
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (Herramienta de exportación de metadatos de Windows Runtime)
La Herramienta de exportación de metadatos de Windows (Winmdexp.exe) transforma un módulo de .NET Framework en un archivo que contiene los metadatos de Windows Runtime. Aunque los ensamblados de .NET Framework y los archivos de metadatos de Windows Runtime utilizan el mismo formato físico, existen diferencias en el contenido de las tablas de metadatos, lo que significa que los ensamblados de .NET Framework no se pueden utilizar de forma automática como componentes de Windows Runtime. El proceso de convertir un módulo de .NET Framework en un componente de Windows Runtime se denomina *exportación*. En .NET Framework 4.5 y .NET Framework 4.5.1, el archivo de metadatos de Windows resultante (.winmd) contiene metadatos y la implementación.  
  
 Cuando se utiliza la plantilla **Componente de Windows Runtime**, que se encuentra en la **Tienda Windows** para C# y Visual Basic en Visual Studio 2013 o Visual Studio 2012, el destino del compilador es un archivo .winmdobj, y en un paso de compilación subsiguiente llama a Winmdexp.exe para exportar el archivo .winmdobj a un archivo .winmd. Esta es la manera recomendada de crear un componente de Windows Runtime. Utilice Winmdexp.exe directamente si desea tener más control sobre el proceso de compilación que proporciona Visual Studio.  
  
 Esta herramienta se instala automáticamente con Visual Studio. Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7). Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).  
  
 En el símbolo del sistema, escriba lo siguiente:  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
winmdexp [options] winmdmodule  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Argumento u opción|Description|  
|------------------------|-----------------|  
|`winmdmodule`|Especifica el módulo (.winmdobj) que se va a exportar. Solo se permite un módulo. Para crear este módulo, utilice la opción del compilador `/target` con el destino de `winmdobj`. Consulte [-target:winmdobj (opciones del compilador de C#)](../../csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) o [-target (Visual Basic)](../../visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Especifica el archivo de documentación XML de salida que Winmdexp.exe va a generar. En .NET Framework 4.5, el archivo de salida es básicamente igual que el archivo de documentación XML de entrada.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|Especifica el nombre del archivo de documentación XML que el compilador generó con `winmdmodule`.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|Especifica el nombre del archivo de base de datos de programa (PDB) que contiene los símbolos para `winmdmodule`.|  
|`/nowarn:` `warning`|Suprime el número de advertencias especificadas. Para *advertencia*, proporcione solo la parte numérica del código de error, sin ceros iniciales.|  
|`/out:` `file`<br /><br /> `/o:` `file`|Especifica el nombre del archivo de metadatos de Windows de salida (.winmd).|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|Especifica el nombre del archivo de base de datos de programa (PDB) de salida que contendrá los símbolos del archivo de metadatos de Windows (.winmd) exportado.|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|Especifica un archivo de metadatos (.winmd o ensamblado) al que hacer referencia durante la exportación. Si utiliza los ensamblados de referencia de "\Archivos de programa (x86)\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5" ("\Archivos de programa\\..." en equipos de 32 bits), incluya las referencias a System.Runtime.dll y a mscorlib.dll.|  
|`/utf8output`|Especifica que los mensajes de salida deben tener la codificación UTF-8.|  
|`/warnaserror+`|Especifica que todas las advertencias se deben tratar como errores.|  
|**@** `responsefile`|Especifica un archivo de respuesta (.rsp) que contiene opciones (y opcionalmente `winmdmodule`). Cada línea de `responsefile` debe contener un solo argumento u opción.|  
  
## <a name="remarks"></a>Comentarios  
 Winmdexp.exe no está diseñado para convertir un ensamblado de .NET Framework. arbitrario en un archivo .winmd. Requiere un módulo que se compila con la opción `/target:winmdobj`, y se aplican restricciones adicionales. La restricción más importante consiste en que todos los tipos que aparecen en la superficie de la API del ensamblado deben ser tipos de Windows Runtime. Para más información, vea la sección "Declarar tipos en componentes de Windows Runtime" del artículo [Componentes de Windows Runtime con C# y Visual Basic](https://docs.microsoft.com/previous-versions/br230301(v=vs.110)).
  
 Al escribir una aplicación de la Tienda Windows 8.x o un componente de Windows Runtime con C# o Visual Basic, .NET Framework ofrece compatibilidad para que la programación con Windows Runtime resulte un proceso más natural. Todo esto se analiza en el artículo [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows en tiempo de ejecución](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md). En dicho proceso, se asignan a algunos tipos de uso general de Windows Runtime a tipos de .NET Framework. Winmdexp.exe invierte este proceso y genera una superficie de API que utiliza los tipos correspondientes de Windows Runtime. Por ejemplo, los tipos que se crean a partir de la interfaz <xref:System.Collections.Generic.IList%601> se asignan a los tipos que se crean a partir de la interfaz <xref:Windows.Foundation.Collections.IVector%601> de Windows Runtime.  
  
## <a name="see-also"></a>Vea también

- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
- [Crear componentes de Windows en tiempo de ejecución en C# y Visual Basic](https://docs.microsoft.com/previous-versions/br230301(v=vs.110))
- [Mensajes de error de Winmdexp.exe](winmdexp-exe-error-messages.md)
- [Herramientas de compilación, implementación y configuración (.NET Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd233108(v=vs.100))
