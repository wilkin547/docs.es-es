---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 00cb62827381146c172e0d15a2c64b167c21f025
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352191"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="4d0d8-101">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d0d8-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="4d0d8-102">Define un nombre de parámetro de tipo y una descripción.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0d8-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d0d8-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d0d8-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d0d8-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4d0d8-105">Nombre del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-105">The name of the type parameter.</span></span> <span data-ttu-id="4d0d8-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="4d0d8-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="4d0d8-107">Descripción del parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d0d8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d0d8-108">Remarks</span></span>  
 <span data-ttu-id="4d0d8-109">Use la etiqueta `<typeparam>` del comentario para un tipo genérico o una declaración de miembro genérico para describir uno de los parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="4d0d8-110">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d0d8-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d0d8-111">Example</span></span>  
 <span data-ttu-id="4d0d8-112">En este ejemplo se usa la etiqueta `<typeparam>` para describir el parámetro `id`.</span><span class="sxs-lookup"><span data-stu-id="4d0d8-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="4d0d8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d0d8-113">See also</span></span>

- [<span data-ttu-id="4d0d8-114">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="4d0d8-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
