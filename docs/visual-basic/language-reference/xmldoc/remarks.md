---
title: '&lt;comentarios&gt; (Visual Basic) | Documentos de Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 89f8d321505b528d07fd04780cec06fb65b0e05e
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="ltremarksgt-visual-basic"></a>&lt;comentarios&gt; (Visual Basic)
Especifica una sección de comentarios del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Descripción del miembro.  
  
## <a name="remarks"></a>Comentarios  
 Utilice la `<remarks>` etiqueta para agregar información sobre un tipo, complementando la información especificada con [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md).  
  
 Esta información aparece en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, consulte [ver la estructura de código](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<remarks>` etiqueta para explicar lo que el `UpdateRecord` método.  
  
 [!code-vb[VbVbcnXmlDocComments Nº&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
