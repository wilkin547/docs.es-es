---
title: <value> - Guía de programación de C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 7f82008d000bf0316b505bfc5d40e9e64b2685a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465198"
---
# <a name="value-c-programming-guide"></a>\<value> (Guía de programación de C#)
## <a name="syntax"></a>Sintaxis  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parámetros  
 `property-description`  
 Una descripción de la propiedad.  
  
## <a name="remarks"></a>Comentarios  
 La etiqueta \<value> le permite describir el valor que representa una propiedad. Tenga en cuenta que cuando agrega una propiedad mediante un asistente de código en el entorno de desarrollo .NET de Visual Studio, agregará una etiqueta [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) para la nueva propiedad. Después, debe agregar manualmente una etiqueta \<value> para describir el valor que representa esa propiedad.  
  
 Compile con [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) para procesar los comentarios de documentación a un archivo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Etiquetas recomendadas para los comentarios de documentación](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
