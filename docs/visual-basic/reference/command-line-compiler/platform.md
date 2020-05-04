---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352341"
---
# <a name="-platform-visual-basic"></a>-platform (Visual Basic)
Especifica qué versión de la plataforma de Common Language Runtime (CLR) puede ejecutar el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`x86`|Compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.|  
|`x64`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.|  
|`Itanium`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.|  
|`arm`|Compila el ensamblado de forma que pueda ejecutarse en un equipo con un procesador ARM (Advanced RISC Machine).|  
|`anycpu`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma. La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits de Windows, y como una aplicación de 64 bits en versiones de 64 bits de Windows. Esta marca es el valor predeterminado.|  
|`anycpu32bitpreferred`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma. La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits y de 64 bits de Windows. Esta marca solo es válida para ejecutables (.EXE) y requiere .NET Framework 4.5.|  
  
## <a name="remarks"></a>Comentarios  
 Use la opción `-platform` para especificar el tipo de procesador de destino del archivo de salida.  
  
 En general, los ensamblados de .NET Framework escritos en Visual Basic se ejecutarán de la misma manera independientemente de la plataforma. Sin embargo, en algunos casos se comportan de forma diferente en distintas plataformas. Estos casos comunes son:  
  
- Estructuras que contengan miembros cuyo tamaño varía según la plataforma, como cualquier tipo de puntero.  
  
- Aritmética de punteros que incluya tamaños constantes.  
  
- Invocación incorrecta de la plataforma o declaraciones COM que utilicen `Integer` para los controladores en lugar de <xref:System.IntPtr>.  
  
- Conversión de <xref:System.IntPtr> a `Integer`.  
  
- Uso de invocación de plataforma o interoperabilidad COM con componentes que no existen en todas las plataformas.  
  
 La opción **-platform** mitigará algunos problemas si ha realizado suposiciones sobre la arquitectura en la que se ejecutará el código. De manera específica:  
  
- Si decide que el destino sea una plataforma de 64 bits pero la aplicación se ejecuta en un equipo de 32 bits, el mensaje de error aparece mucho antes y se centra más bien en el problema que en el error que aparece sin utilizar este modificador.  
  
- Si establece la marca `x86` en la opción y posteriormente la aplicación se ejecuta en un equipo de 64 bits, la aplicación se ejecutará en el subsistema WOW, en lugar de ejecutarse de forma nativa.  
  
 En un sistema operativo de Windows de 64 bits:  
  
- Los ensamblados compilados con `-platform:x86` se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.  
  
- Los ejecutables compilados con `-platform:anycpu` se ejecutarán en el CLR de 64 bits.  
  
- Un archivo DLL compilado con `-platform:anycpu` se ejecutará en el mismo CLR que el proceso en el que se cargó.  
  
- Los archivos ejecutables que se compilan con `-platform:anycpu32bitpreferred` se ejecutarán en el CLR de 32 bits.  
  
 Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en una versión de 64 bits de Windows, vea [Aplicaciones de 64 bits](../../../framework/64-bit-apps.md).  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a>Para establecer -platform en el IDE de Visual Studio  
  
1. En el **Explorador de soluciones**, elija el proyecto, abra el menú **Proyecto** y, después, haga clic en **Propiedades**.  
  
2. En la pestaña **Compilar**, active o desactive la casilla **Preferencia de 32 bits**, o bien elija un valor en la lista **CPU de destino**.  
  
     Para obtener más información, vea [Página Compilar, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar la opción `-platform` del compilador.  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a>Vea también

- [-target (Visual Basic)](target.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
