---
title: -baseaddress (Opciones del compilador de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7cd3269754f783ab8b26683f5215aa81825673e6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="baseaddress-c-compiler-options"></a>/baseaddress (Opciones del compilador de C#)
La opción **/baseaddress** le permite especificar la dirección base preferida para cargar un archivo DLL. Para obtener más información acerca de cuándo y por qué utilizar esta opción, vea [WebLog de Larry Osterman](http://go.microsoft.com/fwlink/?LinkId=107044).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
 `address`  
 La dirección base del archivo DLL. Esta dirección puede especificarse como un número octal, hexadecimal o decimal.  
  
## <a name="remarks"></a>Comentarios  
 La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET Framework.  
  
 Tenga en cuenta que la palabra de orden inferior en esta dirección se redondeará. Por ejemplo, si especifica 0x11110001, se redondeará a 0x11110000.  
  
 Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Dirección base del archivo DLL**.  
  
     Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
