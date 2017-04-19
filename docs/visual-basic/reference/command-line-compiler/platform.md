---
title: /Platform (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6216ee056bc9dd8dd7dfd95b9d5a031880209370
ms.lasthandoff: 03/13/2017

---
# <a name="platform-visual-basic"></a>/platform (Visual Basic)
Especifica qué versión de la plataforma de Common Language Runtime (CLR) puede ejecutar el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`x86`|Compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.|  
|`x64`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.|  
|`Itanium`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.|  
|`arm`|Compila el ensamblado de forma que pueda ejecutarse en un equipo con un procesador ARM (Advanced RISC Machine).|  
|`anycpu`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma. La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits de Windows, y como una aplicación de 64 bits en versiones de 64 bits de Windows. Esta marca es el valor predeterminado.|  
|`anycpu32bitpreferred`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma. La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits y de 64 bits de Windows. Esta marca solo es válida para ejecutables (.EXE) y requiere [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)].|  
  
## <a name="remarks"></a>Comentarios  
 Use la opción `/platform` para especificar el tipo de procesador de destino del archivo de salida.  
  
 En general, los ensamblados de .NET Framework escritos en Visual Basic se ejecutarán de la misma manera independientemente de la plataforma. Sin embargo, en algunos casos se comportan de forma diferente en distintas plataformas. Estos casos comunes son:  
  
-   Estructuras que contengan miembros cuyo tamaño varía según la plataforma, como cualquier tipo de puntero.  
  
-   Aritmética de punteros que incluya tamaños constantes.  
  
-   Incorrecta de la plataforma de invocación o declaraciones COM que utilicen `Integer` para los identificadores en lugar de <xref:System.IntPtr>.</xref:System.IntPtr>  
  
-   Conversión de <xref:System.IntPtr>a `Integer`.</xref:System.IntPtr>  
  
-   Uso de invocación de plataforma o interoperabilidad COM con componentes que no existen en todas las plataformas.  
  
 El **/Platform** opción mitigará algunos problemas si sabe que ha realizado suposiciones acerca de la arquitectura que se ejecutará el código. De manera específica:  
  
-   Si decide que el destino sea una plataforma de 64 bits pero la aplicación se ejecuta en un equipo de 32 bits, el mensaje de error aparece mucho antes y se centra más bien en el problema que en el error que aparece sin utilizar este modificador.  
  
-   Si establece la marca `x86` en la opción y posteriormente la aplicación se ejecuta en un equipo de 64 bits, la aplicación se ejecutará en el subsistema WOW, en lugar de ejecutarse de forma nativa.  
  
 En un sistema operativo de Windows de 64 bits:  
  
-   Los ensamblados compilados con `/platform:x86` se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.  
  
-   Los ejecutables compilados con `/platform:anycpu` se ejecutarán en el CLR de 64 bits.  
  
-   Un archivo DLL compilado con `/platform:anycpu` se ejecutará en el mismo CLR que el proceso en el que se cargó.  
  
-   Los archivos ejecutables que se compilan con `/platform:anycpu32bitpreferred` se ejecutarán en el CLR de 32 bits.  
  
 Para obtener más información sobre cómo desarrollar una aplicación se ejecute en una versión de 64 bits de Windows, consulte [aplicaciones de 64 bits](https://msdn.microsoft.com/library/ms241064).  
  
### <a name="to-set-platform-in-the-visual-studio-ide"></a>Cómo establecer /platform en el IDE de Visual Studio  
  
1.  En **el Explorador de soluciones**, elija el proyecto, abra el **proyecto** menú y, a continuación, haga clic en **propiedades**.  
  
     Para obtener más información, consulte [NIB: administrar propiedades del proyecto con el Diseñador de proyectos](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  En el **compilar** ficha, active o desactive el **preferencia de 32 bits** casilla de verificación, o bien, en la **CPU de destino** , elija un valor.  
  
     Para obtener más información, consulte [página compilación, Diseñador de proyectos (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar la opción `/platform` del compilador.  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [/target (Visual Basic)](target.md)   
 [Compilador de línea de comandos de Visual Basic](index.md)   
 [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
