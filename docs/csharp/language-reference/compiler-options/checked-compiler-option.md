---
title: -checked (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c6cfc54c2dbd3e14d874d7684fdc75a972260cc3
ms.lasthandoff: 03/13/2017

---
# <a name="checked-c-compiler-options"></a>/checked (Opciones del compilador de C#)
La opción **/checked** especifica si una instrucción aritmética de enteros que produce un valor fuera del intervalo del tipo de datos y que no está en el ámbito de las palabras clave [checked](../../../csharp/language-reference/keywords/checked.md) o [unchecked](../../../csharp/language-reference/keywords/unchecked.md) provocará una excepción en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/checked[+ | -]  
```  
  
## <a name="remarks"></a>Comentarios  
 Una instrucción de aritmética de enteros que está en el ámbito de la palabra clave `checked` o `unchecked` no está sujeta al efecto de la opción **/checked**.  
  
 Si una instrucción de aritmética de enteros que no está en el ámbito de la palabra clave `checked` o `unchecked` produce un valor fuera del intervalo del tipo de datos, y si se usa **/checked+** (**/checked**) en la compilación, la instrucción provoca una excepción en tiempo de ejecución. Si se usa **/checked-** en la compilación, la instrucción no produce una excepción en tiempo de ejecución.  
  
 El valor predeterminado para esta opción es **/checked-**. Un escenario habitual para el uso de **/checked-** es la compilación de aplicaciones de gran tamaño. A veces se usan herramientas automatizadas para generar compilar estas aplicaciones, y estas herramientas podrían establecer automáticamente **/checked** en +. Para reemplazar el valor predeterminado global de la herramienta, especifique **/checked-**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto. Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](https://docs.microsoft.com/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Comprobar el desbordamiento y subdesbordamiento aritmético**.  
  
 Para obtener acceso a esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `t2.cs`. El uso de `/checked` en el comando especifica que cualquier instrucción de aritmética de enteros del archivo que no esté en el ámbito de la palabra clave `checked` o `unchecked` y que produzca un valor fuera del intervalo del tipo de datos provocará una excepción en tiempo de ejecución.  
  
```  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)
