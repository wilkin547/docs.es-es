---
title: '&lt;param&gt; (Visual Basic) | Documentos de Microsoft'
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
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
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
ms.openlocfilehash: 41852a7fc41595050940d87f9e741df5cb23361c
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="ltparamgt-visual-basic"></a>&lt;param&gt; (Visual Basic)
Define un nombre de parámetro y una descripción.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `name`  
 El nombre de un parámetro de método. Ponga el nombre entre comillas dobles ("").  
  
 `description`  
 Una descripción para el parámetro.  
  
## <a name="remarks"></a>Comentarios  
 La `<param>` etiqueta debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.  
  
 El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:  
  
-   Información de parámetros de IntelliSense. Para obtener más información, vea [Usar IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense).  
  
-   Examinador de objetos. Para obtener más información, vea [Ver la estructura del código](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code).  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<param>` etiqueta para describir la `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments Nº&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
