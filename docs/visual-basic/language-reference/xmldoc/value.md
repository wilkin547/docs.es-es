---
title: '&lt;valor&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a72c6330596e59d26fbae9d13f6b9c8b1987e519
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltvaluegt-visual-basic"></a>&lt;valor&gt; (Visual Basic)
Especifica la descripción de una propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `property-description`  
 Una descripción de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 Use la `<value>` etiquetas para describir una propiedad. Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad. A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.  
  
 Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
