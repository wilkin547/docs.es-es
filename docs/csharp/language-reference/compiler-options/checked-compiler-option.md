---
title: "/checked (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/checked"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "checked compiler option [C#]"
  - "-checked compiler option [C#]"
  - "/checked compiler option [C#]"
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# /checked (C# Compiler Options)
La opción **\/checked** especifica si una instrucción de aritmética de enteros que produzca un valor fuera del alcance del tipo de datos y que no pertenezca al ámbito de las palabras clave [checked](../../../csharp/language-reference/keywords/checked.md) o [unchecked](../../../csharp/language-reference/keywords/unchecked.md) causará una excepción en tiempo de ejecución.  
  
## Sintaxis  
  
```  
/checked[+ | -]  
```  
  
## Comentarios  
 Una instrucción de aritmética de enteros que pertenece al ámbito de las palabras clave `checked` o `unchecked` no se ve afectada por la opción **\/checked**.  
  
 Si una instrucción de aritmética de enteros no comprendida en el ámbito de las palabras clave `checked` o `unchecked` da como resultado un valor situado fuera del intervalo del tipo de datos, y se utiliza **\/checked\+** \(**\/checked**\) en la compilación, esa instrucción causa una excepción en tiempo de ejecución.  Si se utiliza **\/checked\-** en la compilación, la instrucción no causará ninguna excepción en tiempo de ejecución.  
  
 El valor predeterminado para esta opción es **\/checked\-**.  Un posible escenario para usar **\/checked\-** es la compilación de grandes aplicaciones.  A veces se usan herramientas automatizadas para compilar dichas aplicaciones, y una herramienta de este tipo puede establecer **\/checked** automáticamente en \+.  Puede invalidar el valor predeterminado global de la herramienta especificando **\/checked\-**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  Para obtener más información, vea [Compilar \(Página, Diseñador de proyectos\) \(C\#\)](/visual-studio/ide/reference/build-page-project-designer-csharp).  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **Comprobar el desbordamiento y subdesbordamiento aritmético**.  
  
 Para tener acceso a esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## Ejemplo  
 El comando siguiente compila `t2.cs`.  El uso de `/checked` en el comando especifica que cualquier instrucción de aritmética de enteros en el archivo que no pertenezca al ámbito de las palabras clave `checked` o `unchecked` y dé como resultado un valor situado fuera del intervalo del tipo de datos causará una excepción en tiempo de ejecución.  
  
```  
csc t2.cs /checked  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7)