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
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="b878a-102">&lt;valor&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b878a-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="b878a-103">Especifica la descripción de una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b878a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b878a-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b878a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b878a-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b878a-106">Una descripción de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b878a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b878a-107">Remarks</span></span>  
 <span data-ttu-id="b878a-108">Use la `<value>` etiquetas para describir una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="b878a-109">Tenga en cuenta que cuando se agrega una propiedad mediante el Asistente para código en el entorno de desarrollo de Visual Studio, se agregará un [ \<resumen >](../../../visual-basic/language-reference/xmldoc/summary.md) etiqueta para la nueva propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="b878a-110">A continuación, debe agregar manualmente un `<value>` etiquetas para describir el valor que representa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b878a-111">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="b878a-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b878a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b878a-112">Example</span></span>  
 <span data-ttu-id="b878a-113">Este ejemplo se utiliza la `<value>` etiquetas para describir qué valor la `Counter` suspensiones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b878a-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b878a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b878a-114">See Also</span></span>  
 [<span data-ttu-id="b878a-115">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="b878a-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
