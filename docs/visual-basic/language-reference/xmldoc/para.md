---
description: 'Más información acerca de: <para> (Visual Basic)'
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 51dd9ff300d980b4c0576566cad5d17375889ba1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740774"
---
# <a name="para-visual-basic"></a>\<para> (Visual Basic)

Especifica que el contenido está formateado como un párrafo.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a>Parámetros  

 `content`  
 El texto del párrafo.  
  
## <a name="remarks"></a>Comentarios  

 La etiqueta `<para>` se usa dentro de otra etiqueta, como [\<summary>](summary.md), [\<remarks>](remarks.md) o [\<returns>](returns.md), y permite dar una estructura al texto.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<para>` etiqueta para dividir la sección Comentarios del `UpdateRecord` método en dos párrafos.  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
