---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352170"
---
# <a name="value-visual-basic"></a>> de valor \<(Visual Basic)
Especifica la descripción de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parámetros  
 `property-description`  
 Una descripción de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Use la etiqueta `<value>` para describir una propiedad. Tenga en cuenta que al agregar una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará una etiqueta [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) para la nueva propiedad. Después, debe agregar manualmente una etiqueta de `<value>` para describir el valor que representa la propiedad.  
  
 Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa la etiqueta `<value>` para describir el valor que contiene la propiedad `Counter`.  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>Vea también

- [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/index.md)
