---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad3ca7775512623de43c7fe6b7fe1cf481ccca87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
