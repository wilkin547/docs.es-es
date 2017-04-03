---
title: -main (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /main
dev_langs:
- CSharp
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
caps.latest.revision: 14
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
ms.openlocfilehash: fa8c02a6521b65e2cc4f7c8d779c1091ce399fba
ms.lasthandoff: 03/13/2017

---
# <a name="main-c-compiler-options"></a>/main (Opciones del compilador de C#)
Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método **Main**.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/main:class  
```  
  
## <a name="arguments"></a>Argumentos  
 `class`  
 Tipo que contiene el método **Main**.  
  
## <a name="remarks"></a>Comentarios  
 Si la compilación incluye más de un tipo con un método [Main](../../../csharp/programming-guide/main-and-command-args/index.md), puede especificar el tipo que contiene el método **Main** que quiere usar como punto de entrada en el programa.  
  
 Esta opción se usa al compilar un archivo .exe.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Objeto de inicio**.  
  
     Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `t2.cs` y `t3.cs` y especifique que el método **Main** se encuentra en `Test2`:  
  
```  
csc t2.cs t3.cs /main:Test2  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
