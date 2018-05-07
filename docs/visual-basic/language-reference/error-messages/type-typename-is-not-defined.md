---
title: Tipo de &#39; &lt;typename&gt; &#39; no está definido
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>Tipo de &#39; &lt;typename&gt; &#39; no está definido
La instrucción ha hecho referencia a un tipo que no se ha definido. Puede definir un tipo en una instrucción de declaración como `Enum`, `Structure`, `Class`, o `Interface`.  
  
 **Id. de error:** BC30002  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que la definición de tipo y su referencia utilizan la misma ortografía.  
  
-   Asegúrese de que la definición de tipo es accesible para la referencia. Por ejemplo, si el tipo está en otro módulo y se ha declarado `Private`, mueva la definición de tipo al que hace referencia a módulo o declárelo `Public`.  
  
-   Asegúrese de que el espacio de nombres del tipo no se vuelve a definir dentro de su proyecto. Si es así, utilice el `Global` palabra clave para calificar totalmente el nombre de tipo. Por ejemplo, si un proyecto que define un espacio de nombres denominado `System`, el <xref:System.Object?displayProperty=nameWithType> tipo no son accesibles a menos que esté completo con el `Global` palabra clave: `Global.System.Object`.  
  
-   Si el tipo está definido, pero no se registra la biblioteca de objetos o la biblioteca de tipos en el que se define en Visual Basic, haga clic **Agregar referencia** en el **proyecto** menú y, a continuación, seleccione el objeto apropiado biblioteca o biblioteca de tipos.  
  
-   Asegúrese de que el tipo está en un ensamblado que forma parte del perfil de .NET Framework de destino. Para obtener más información, consulte [Solucionar problemas de versión de .NET Framework de destino](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).  
  
## <a name="see-also"></a>Vea también  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class (instrucción)](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Administrar referencias en un proyecto](/visualstudio/ide/managing-references-in-a-project)
