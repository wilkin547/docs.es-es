---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d7fb980545a532e39310ea3e9d663a2b5a81a006
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968457"
---
# <a name="typeparam-visual-basic"></a>\<typeparam > (Visual Basic)
Define un nombre de parámetro de tipo y descripción.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `name`  
 El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Una descripción del parámetro de tipo.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<typeparam>` etiqueta en el comentario de un tipo genérico o declaración de miembro genérico describir uno de los parámetros de tipo.  
  
 Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `<typeparam>` etiquetas para describir el `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Vea también
- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
