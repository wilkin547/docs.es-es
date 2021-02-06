---
description: 'Más información acerca de: <typeparam> (Visual Basic)'
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: efb4394ee2badcf52bac75d7d9e317c732789746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640269"
---
# <a name="typeparam-visual-basic"></a>\<typeparam> (Visual Basic)

Define un nombre de parámetro de tipo y una descripción.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a>Parámetros  

 `name`  
 El nombre del parámetro de tipo. Ponga el nombre entre comillas dobles (" ").  
  
 `description`  
 Descripción del parámetro de tipo.  
  
## <a name="remarks"></a>Observaciones  

 Use la `<typeparam>` etiqueta del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<typeparam>` etiqueta para describir el `id` parámetro.  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
