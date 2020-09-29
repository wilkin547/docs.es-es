---
description: -nowarn (Opciones del compilador de C#)
title: -nowarn (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nowarn
helpviewer_keywords:
- nowarn compiler option [C#]
- /nowarn compiler option [C#]
- -nowarn compiler option [C#]
ms.assetid: 6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4
ms.openlocfilehash: 31a7ee5eacb2e7cd6b24c4a2276ce6e07fcc67e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194029"
---
# <a name="-nowarn-c-compiler-options"></a>-nowarn (Opciones del compilador de C#)

La opción **-nowarn** permite impedir que el compilador muestre una o más advertencias. Separe varios números de advertencia con una coma.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nowarn:number1[,number2,...]  
```  
  
## <a name="arguments"></a>Argumentos  

 `number1`, `number2`  
 Números de advertencia que quiere que el compilador suprima.  
  
## <a name="remarks"></a>Comentarios  

 Solo debe especificar la parte numérica del identificador de advertencia. Por ejemplo, si quiere suprimir CS0028, puede especificar `-nowarn:28`.  
  
 El compilador omitirá silenciosamente los números de advertencia pasados a `-nowarn` que eran válidos en versiones anteriores, pero que se han quitado del compilador. Por ejemplo, CS0679 era válido en el compilador de Visual Studio .NET 2002, pero se ha eliminado posteriormente.  
  
 Las advertencias siguientes no se pueden suprimir mediante la opción `-nowarn`:  
  
- Advertencia del compilador (nivel 1) CS2002  
  
- Advertencia del compilador (nivel 1) CS2023  
  
- Advertencia del compilador (nivel 1) CS2029  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto. Para obtener más información, vea [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Modifique la propiedad **Suprimir advertencias**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
- [Errores del compilador de C#](../compiler-messages/index.md)
