---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4bcfe96361de9e196cb684ac4ba734f82442e25c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825565"
---
# <a name="param-visual-basic"></a><span data-ttu-id="0f225-102">\<param > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f225-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="0f225-103">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="0f225-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f225-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f225-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f225-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f225-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="0f225-106">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="0f225-106">The name of a method parameter.</span></span> <span data-ttu-id="0f225-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="0f225-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="0f225-108">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="0f225-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f225-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f225-109">Remarks</span></span>  
 <span data-ttu-id="0f225-110">El `<param>` etiqueta debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="0f225-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="0f225-111">El texto para el `<param>` etiqueta aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="0f225-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="0f225-112">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="0f225-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="0f225-113">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="0f225-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="0f225-114">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="0f225-114">Object Browser.</span></span> <span data-ttu-id="0f225-115">Para obtener más información, vea [Ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="0f225-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="0f225-116">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="0f225-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f225-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f225-117">Example</span></span>  
 <span data-ttu-id="0f225-118">Este ejemplo se usa el `<param>` etiquetas para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="0f225-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="0f225-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f225-119">See also</span></span>

- [<span data-ttu-id="0f225-120">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="0f225-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
