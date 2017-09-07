---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /nostdlib
dev_langs:
- CSharp
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: 18
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1d500e2e55ab3117aa674e11d6cdd25703035879
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="nostdlib-c-compiler-options"></a>/nostdlib (Opciones del compilador de C#)
**/nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.  
  
 Si no se especifica **/nostdlib**, el archivo mscorlib.dll se importará en el programa (equivale a especificar **/nostdlib-**). Especificar **/nostdlib** es lo mismo que especificar **/nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar** .  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)

