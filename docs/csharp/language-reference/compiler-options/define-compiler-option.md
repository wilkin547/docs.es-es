---
description: -define (Opciones del compilador de C#)
title: -define (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /define
helpviewer_keywords:
- -define compiler option [C#]
- /define compiler option [C#]
- -d compiler option [C#]
- define compiler option [C#]
- /d compiler option [C#]
- d compiler option [C#]
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
ms.openlocfilehash: 3b7a1c6e92d2c60ce289f29044774c3aa42ca84f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125883"
---
# <a name="-define-c-compiler-options"></a>-define (Opciones del compilador de C#)
La opción **-define** define `name` como un símbolo en todos los archivos de código fuente de su programa.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-define:name[;name2]  
```  
  
## <a name="arguments"></a>Argumentos  
 `name`, `name2`  
 El nombre de uno o más símbolos que quiere definir.  
  
## <a name="remarks"></a>Observaciones  
 La opción **-define** provoca el mismo efecto que usar una directiva del preprocesador [#define](../preprocessor-directives/preprocessor-define.md), salvo que la opción del compilador está en vigor para todos los archivos del proyecto. Un símbolo permanece definido en un archivo de origen hasta que una directiva [#undef](../preprocessor-directives/preprocessor-undef.md) en el archivo de origen quita la definición. Cuando usa la opción -define, una directiva `#undef` en un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con [#if](../preprocessor-directives/preprocessor-if.md), [#else](../preprocessor-directives/preprocessor-else.md), [#elif](../preprocessor-directives/preprocessor-elif.md) y [#endif](../preprocessor-directives/preprocessor-endif.md) para compilar los archivos de origen condicionalmente.  
  
 **-d** es la forma abreviada de **-define**.  
  
 Se pueden definir varios símbolos con **-define** mediante un punto y coma o una coma para separar los nombres de símbolos. Por ejemplo:  
  
```console  
-define:DEBUG;TUESDAY  
```  
  
 El propio compilador de C# no define ningún símbolo o macro que puede usar en su código fuente; todas las definiciones de símbolo deben definirse por el usuario.  
  
> [!NOTE]
> El valor `#define` de C# no permite que se le proporcione un valor a un símbolo; como en lenguajes como C++. Por ejemplo, `#define` no puede usarse para crear una macro o para definir una constante. Si necesita definir una constante, use una variable `enum`. Si quiere crear una macro de estilo de C++, considere alternativas como genéricos. Como las macros son notoriamente propensas a errores, C# deshabilita su uso pero proporciona alternativas más seguras.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. En la pestaña **Compilar**, escriba el símbolo que va a definirse en el cuadro **Símbolos de compilación condicional**. Por ejemplo, si está usando el ejemplo de código siguiente, simplemente escriba `xx` en el cuadro de texto.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## <a name="example"></a>Ejemplo  
  
```csharp  
// preprocessor_define.cs  
// compile with: -define:xx  
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

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
