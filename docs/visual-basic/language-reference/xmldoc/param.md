---
title: <param> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c62eab6b1fb1ba1cc7de83c12d7205cf0bbe46fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524720"
---
# <a name="param-visual-basic"></a><span data-ttu-id="742a9-102">\<param > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="742a9-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="742a9-103">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="742a9-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="742a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="742a9-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="742a9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="742a9-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="742a9-106">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="742a9-106">The name of a method parameter.</span></span> <span data-ttu-id="742a9-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="742a9-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="742a9-108">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="742a9-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="742a9-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="742a9-109">Remarks</span></span>  
 <span data-ttu-id="742a9-110">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="742a9-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="742a9-111">El texto de la etiqueta `<param>` aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="742a9-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="742a9-112">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="742a9-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="742a9-113">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="742a9-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="742a9-114">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="742a9-114">Object Browser.</span></span> <span data-ttu-id="742a9-115">Para obtener más información, vea [Ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="742a9-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="742a9-116">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="742a9-116">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="742a9-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="742a9-117">Example</span></span>  
 <span data-ttu-id="742a9-118">En este ejemplo se usa la etiqueta `<param>` para describir el parámetro `id`.</span><span class="sxs-lookup"><span data-stu-id="742a9-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="742a9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="742a9-119">See also</span></span>

- [<span data-ttu-id="742a9-120">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="742a9-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
