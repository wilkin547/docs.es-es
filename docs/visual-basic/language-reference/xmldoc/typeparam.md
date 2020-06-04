---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411491"
---
# <a name="typeparam-visual-basic"></a>\<typeparam> (Visual Basic)
Define un nombre de parámetro de tipo y una descripción.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Parámetros  
 `name`  
 Nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Descripción del parámetro de tipo.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<typeparam>` etiqueta del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.  
  
 Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la `<typeparam>` etiqueta para describir el `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Consulte también

- [Etiquetas de comentario XML](index.md)
