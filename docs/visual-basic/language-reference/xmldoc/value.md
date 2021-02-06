---
description: 'Más información acerca de: <value> (Visual Basic)'
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 80a3ef875eea4418d28d60dac1818f3390c361ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640256"
---
# <a name="value-visual-basic"></a>\<value> (Visual Basic)

Especifica la descripción de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parámetros  

 `property-description`  
 Una descripción de la propiedad.  
  
## <a name="remarks"></a>Comentarios  

 Use la `<value>` etiqueta para describir una propiedad. Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una [\<summary>](summary.md) etiqueta para la nueva propiedad. Después, debe agregar manualmente una etiqueta `<value>` para describir el valor que representa esa propiedad.  
  
 Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa la `<value>` etiqueta para describir el valor que `Counter` contiene la propiedad.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas de comentario XML](index.md)
