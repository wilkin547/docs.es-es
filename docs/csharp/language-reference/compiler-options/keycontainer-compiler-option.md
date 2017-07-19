---
title: -keycontainer (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
dev_langs:
- CSharp
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 30b851a3e44c90582227beda7245a7c4b0d57b47
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="keycontainer-c-compiler-options"></a>/keycontainer (Opciones del compilador de C#)
Especifica el nombre del contenedor de claves criptográficas.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/keycontainer:string  
```  
  
## <a name="arguments"></a>Argumentos  
 `string`  
 El nombre del contenedor de claves de nombre seguro.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se usa la opción **/keycontainer**, el compilador crea un componente compartible insertando una clave pública desde el contenedor especificado en el manifiesto del ensamblado y firma el ensamblado final con la clave privada. Para generar un archivo de clave, escriba sn -k `file` en la línea de comandos. sn -i instala el par de claves en un contenedor.  
  
 Si se compila con [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), el nombre del archivo de claves se mantiene en el módulo y se incorpora al ensamblado al compilar este módulo en un ensamblado con [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 También se puede especificar esta opción como un atributo personalizado (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>) en el código fuente de cualquier módulo del Lenguaje Intermedio de Microsoft (MSIL).  
  
 También se puede pasar la información de cifrado al compilador con [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md). Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) si quiere agregar la clave pública al manifiesto del ensamblado pero retrasar la firma del ensamblado hasta que se haya probado.  
  
 Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](https://msdn.microsoft.com/library/xwb8f617) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Esta opción del compilador no está disponible en el entorno de desarrollo de Visual Studio.  
  
 Puede tener acceso mediante programación a esta opción del compilador con <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
