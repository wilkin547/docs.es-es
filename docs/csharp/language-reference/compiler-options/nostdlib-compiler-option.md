---
title: -nostdlib (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /nostdlib
helpviewer_keywords:
- nostdlib compiler option [C#]
- -nostdlib compiler option [C#]
- /nostdlib compiler option [C#]
ms.assetid: ec197989-fa49-4725-a455-e06b551eb65f
ms.openlocfilehash: 1dc0ab70ca28626c4a3f505c13ec1d6f828a4b05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-nostdlib-c-compiler-options"></a>-nostdlib (Opciones del compilador de C#)
**-nostdlib** impide la importación del archivo mscorlib.dll, que define el espacio de nombres System completo.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-nostdlib[+ | -]  
```  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.  
  
 Si no se especifica **-nostdlib**, el archivo mscorlib.dll se importará en el programa (equivale a especificar **-nostdlib-**). Especificar **-nostdlib** es lo mismo que especificar **-nostdlib+**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar** .  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **No hacer referencia al archivo mscorlib.dll** .  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.NoStdLib%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)
