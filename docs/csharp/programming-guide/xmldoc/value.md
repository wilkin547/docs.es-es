---
title: '&lt;value&gt; (Guía de programación de C#)'
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 22de15560d6db6e8a70cea744dd9d85359336306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="ltvaluegt-c-programming-guide"></a>&lt;value&gt; (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>Parámetros  
 `property-description`  
 Una descripción de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<value> le permite describir el valor que representa una propiedad. Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad. Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
