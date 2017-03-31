---
title: -target:appcontainerexe (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 168771506692308bc9b031df5c059e58e8d190b1
ms.lasthandoff: 03/13/2017

---
# <a name="targetappcontainerexe-c-compiler-options"></a>/target:appcontainerexe (Opciones del compilador de C#)
Si usa la opción del compilador **/target:appcontainerexe**, este crea un archivo ejecutable de Windows (.exe) que se debe ejecutar en un contenedor de la aplicación. Esta opción equivale a [/target: winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), pero está diseñada para las aplicaciones de la [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/target:appcontainerexe  
```  
  
## <a name="remarks"></a>Comentarios  
 Para exigir que la aplicación se ejecute en un contenedor de la aplicación, esta opción establece un bit en el archivo [portable ejecutable](http://go.microsoft.com/fwlink/p/?LinkId=236960) (PE). Cuando se establece ese bit, se produce un error si el método CreateProcess intenta iniciar el archivo ejecutable fuera de un contenedor de la aplicación.  
  
 A menos que use la opción [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md), el archivo de salida toma el nombre del archivo de entrada que contiene el método [Main](../../../csharp/programming-guide/main-and-command-args/index.md).  
  
 Cuando se especifica esta opción en un símbolo del sistema, todos los archivos hasta la siguiente opción **/out** o **/target** se usan para crear el archivo ejecutable.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>Para establecer esta opción del compilador en el IDE  
  
1.  En el **Explorador de soluciones**, abra el menú contextual del proyecto y después elija **Propiedades**.  
  
2.  En la pestaña **Aplicación**, en la lista **Tipo de resultado**, elija **Aplicación de la Tienda Windows**.  
  
     Esta opción solo está disponible para las plantillas de aplicaciones de la [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)].  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, consulte <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `filename.cs` en un archivo ejecutable de Windows que solo se puede ejecutar en un contenedor de la aplicación.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [/target (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  (/target [Opciones del compilador de C#])  
 [/target:winexe (C# Compiler Options)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  (/target:winexe [Opciones del compilador de C#])  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
