---
title: -filealign (C# Compiler Options) (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /filealign
dev_langs:
- CSharp
helpviewer_keywords:
- /alignment compiler option [C#]
- filealign compiler option [C#]
- -filealign compiler option [C#]
- /sections compiler option [C#]
- alignment compiler option [C#]
- sections compiler option [C#]
- -sections compiler option [C#]
- /filealign compiler option [C#]
- file sharing [C#]
- -alignment compiler option [C#]
- section alignment [C#]
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
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
ms.openlocfilehash: 83569fa264ba3ed6e271281885940a70a5354840
ms.lasthandoff: 03/13/2017

---
# <a name="filealign-c-compiler-options"></a>/filealign (Opciones del compilador de C#)
La opción **/filealign** permite especificar el tamaño de las secciones en el archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>Argumentos  
 `number`  
 Un valor que especifica el tamaño de las secciones del archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.  
  
## <a name="remarks"></a>Comentarios  
 Cada sección se alineará en un límite que es un múltiplo del valor **/filealign**. No hay ningún valor predeterminado fijo. Si no se especifica **/filealign**, el Common Language Runtime elige un valor predeterminado en tiempo de compilación.  
  
 Al especificar el tamaño de la sección, el tamaño del archivo de salida se ve afectado. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.  
  
 Use [DUMPBIN](https://docs.microsoft.com/cpp/build/reference/dumpbin-options) para ver información sobre las secciones en el archivo de salida.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Alineación de archivo**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
