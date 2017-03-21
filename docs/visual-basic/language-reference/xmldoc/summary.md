---
title: '&lt;resumen&gt; (Visual Basic) | Documentos de Microsoft'
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.openlocfilehash: ad2053e21e58c49205fe869a484cb2dffd2169ee
ms.lasthandoff: 03/13/2017

---
# <a name="ltsummarygt-visual-basic"></a>&lt;resumen&gt; (Visual Basic)
Especifica el resumen del miembro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `description`  
 Resumen del objeto.  
  
## <a name="remarks"></a>Comentarios  
 Utilice la `<summary>` etiqueta para describir un tipo o miembro de tipo. Utilice [ \<comentarios >](../../../visual-basic/language-reference/xmldoc/remarks.md) para agregar información adicional a una descripción de tipo.  
  
 El texto de la `<summary>` etiqueta es la única fuente de información sobre el tipo en IntelliSense y también se muestra en el Examinador de objetos. Para obtener información sobre el Examinador de objetos, consulte [ver la estructura de código](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<summary>` etiqueta para describir la `ResetCounter` método y `Counter` propiedad.  
  
 [!code-vb[1 VbVbcnXmlDocComments](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
