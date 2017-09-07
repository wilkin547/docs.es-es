---
title: -delaysign (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce4c9fbb14081764985f3b02988dff9ee272c451
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="delaysign-c-compiler-options"></a>/delaysign (Opciones del compilador de C#)
Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Use **/delaysign-** para firmar completamente un ensamblado. Use **/delaysign+** si quiere incluir solo la clave pública en el ensamblado. El valor predeterminado es **/delaysign-**.  
  
## <a name="remarks"></a>Comentarios  
 La opción **/delaysign** no tiene ningún efecto a menos que se use con [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) o [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  
  
 Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada. La firma digital resultante se almacena en el archivo que contiene el manifiesto. Cuando se retrasa la firma de un ensamblado, el compilador no calcula ni almacena la firma, sino que reserva espacio en el archivo para que la firma se pueda agregar más tarde.  
  
 Por ejemplo, si se usa **/delaysign+**, los evaluadores podrán colocar el ensamblado en la memoria caché global. Después de realizar las pruebas, coloque la clave privada en el ensamblado mediante la utilidad [Assembly Linker](https://msdn.microsoft.com/library/c405shex) para firmar el ensamblado por completo.  
  
 Para obtener más información, vea [Crear y usar ensamblados con nombre seguro](https://msdn.microsoft.com/library/xwb8f617) y [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md) (Retrasar la firma de un ensamblado).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Modifique la propiedad **Solo retrasar firma**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

