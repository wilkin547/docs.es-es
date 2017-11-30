---
title: -define (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d4c7e4e646e6796cff6bbfbe05038ff361fa80c3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="define-c-compiler-options"></a>/define (Opciones del compilador de C#)
La opción **/define** define `name` como un símbolo en todos los archivos de código fuente de su programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/define:name[;name2]  
```  
  
## <a name="arguments"></a>Argumentos  
 `name`, `name2`  
 El nombre de uno o más símbolos que quiere definir.  
  
## <a name="remarks"></a>Comentarios  
 La opción **/define** tiene el mismo efecto que usar una directiva del preprocesador [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) excepto que la opción del compilador está en vigor para todos los archivos del proyecto. Un símbolo permanece definido en un archivo de origen hasta que una directiva [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) en el archivo de origen quita la definición. Cuando usa la opción /define, una directiva `#undef` en un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) y [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) para compilar los archivos de origen condicionalmente.  
  
 **/d** es la forma abreviada de **/define**.  
  
 Se pueden definir varios símbolos con **/define** mediante un punto y coma o una coma para separar los nombres de símbolos. Por ejemplo:  
  
```console  
/define:DEBUG;TUESDAY  
```  
  
 El propio compilador de C# no define ningún símbolo o macro que puede usar en su código fuente; todas las definiciones de símbolo deben definirse por el usuario.  
  
> [!NOTE]
>  El valor `#define` de C# no permite que se le proporcione un valor a un símbolo; como en lenguajes como C++. Por ejemplo, `#define` no puede usarse para crear una macro o para definir una constante. Si necesita definir una constante, use una variable `enum`. Si quiere crear una macro de estilo de C++, considere alternativas como genéricos. Como las macros son notoriamente propensas a errores, C# deshabilita su uso pero proporciona alternativas más seguras.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  En la pestaña **Compilar**, escriba el símbolo que va a definirse en el cuadro **Símbolos de compilación condicional**. Por ejemplo, si está usando el ejemplo de código siguiente, simplemente escriba `xx` en el cuadro de texto.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
// preprocessor_define.cs  
// compile with: /define:xx  
// or uncomment the next line  
// #define xx  
using System;  
public class Test   
{  
    public static void Main()   
    {  
        #if (xx)   
            Console.WriteLine("xx defined");  
        #else  
            Console.WriteLine("xx not defined");  
        #endif  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
