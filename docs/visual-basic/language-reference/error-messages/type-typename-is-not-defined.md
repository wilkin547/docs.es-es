---
title: "Tipo &quot;&lt;typename&gt;&quot; no está definido | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 09aa7c535fd5e17ddcd0e743fb5ec17ebadd4f7d
ms.lasthandoff: 03/13/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Tipo '&lt;typename&gt;' no está definido
La instrucción hace referencia a un tipo que no se ha definido. Puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class`, o `Interface`.  
  
 **Id. de error:** BC30002  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que la definición de tipo y su referencia utilizan la misma ortografía.  
  
-   Asegúrese de que la definición de tipo es accesible para la referencia. Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private`, mover la definición de tipo al módulo que hace la referencia o declárelo `Public`.  
  
-   Asegúrese de que el espacio de nombres del tipo no se vuelve a definir dentro de su proyecto. Si es así, utilice el `Global` palabra clave para calificar el nombre de tipo. Por ejemplo, si un proyecto define un espacio de nombres `System`, el <xref:System.Object?displayProperty=fullName>tipo no puede tener acceso a menos que esté completo con el `Global` palabra clave: `Global.System.Object`.</xref:System.Object?displayProperty=fullName>  
  
-   Si el tipo está definido, pero no se registra la biblioteca de objetos o tipos en la que se define en [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], haga clic en **Agregar referencia** en el **proyecto** menú y, a continuación, seleccione la biblioteca de objetos adecuado o la biblioteca de tipos.  
  
-   Asegúrese de que el tipo está en un ensamblado que es parte del perfil de .NET Framework de destino. Para obtener más información, consulte [solución de problemas de errores de destino de .NET Framework](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Vea también  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Administrar referencias en un proyecto](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)
