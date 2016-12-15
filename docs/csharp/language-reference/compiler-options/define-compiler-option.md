---
title: "/define (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/define"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-define compiler option [C#]"
  - "/define compiler option [C#]"
  - "-d compiler option [C#]"
  - "define compiler option [C#]"
  - "/d compiler option [C#]"
  - "d compiler option [C#]"
ms.assetid: f17d7b4d-82d0-4133-8563-68cced1cac6e
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /define (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La opción **\/define** define `name` como un símbolo en todos los archivos de código fuente del programa.  
  
## Sintaxis  
  
```  
/define:name[;name2]  
```  
  
## Argumentos  
 `name`, `name2`  
 Nombre de uno o varios símbolos que desea definir.  
  
## Comentarios  
 La opción **\/define** produce el mismo efecto que una directiva de preprocesador [\#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), con la diferencia de que la opción del compilador está activada para todos los archivos del proyecto.  Un símbolo permanece definido en un archivo de código fuente hasta que una directiva [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) del archivo de código fuente quita la definición.  Si se utiliza la opción \/define, la directiva `#undef` de un archivo no tiene ningún efecto en otros archivos de código fuente del proyecto.  
  
 Se pueden utilizar símbolos creados por esta opción con [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), [\#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) y [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) para compilar archivos de código fuente de forma condicional.  
  
 **\/d** es la forma abreviada de **\/define**.  
  
 Se pueden definir múltiples símbolos con **\/define** utilizando punto y coma o coma para separar los nombres de símbolos.  Por ejemplo:  
  
```  
/define:DEBUG;TUESDAY  
```  
  
 El propio compilador de C\# no define ningún símbolo ni macro que se pueda utilizar en el código fuente; todas las definiciones de símbolos deben estar definidas por el usuario.  
  
> [!NOTE]
>  La directiva `#define` de C\# no permite que se le proporcione un valor a un símbolo, igual que sucede en otros lenguajes como C\+\+.  Por ejemplo, `#define` no se puede utilizar para crear una macro o definir una constante.  Si tiene que definir una constante, utilice una variable `enum`.  Si desea crear una macro de estilo C\+\+, considere alternativas como el uso de genéricos.  Ya que las macros son notoriamente propensas a errores, C\# no permite su uso, pero proporciona alternativas más seguras.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  En la ficha **Generar**, escriba el símbolo que se va a definir en el cuadro **Símbolos de compilación condicional**.  Por ejemplo, si está utilizando el ejemplo de código siguiente, escriba solamente `xx` en el cuadro de texto.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DefineConstants%2A>.  
  
## Ejemplo  
  
```  
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
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)