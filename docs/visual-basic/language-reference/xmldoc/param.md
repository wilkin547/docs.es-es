---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 19300a928a59c7259f81b282bd28d9bdd447d76b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872622"
---
# <a name="param-visual-basic"></a><span data-ttu-id="53b45-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="53b45-101">\<param> (Visual Basic)</span></span>

<span data-ttu-id="53b45-102">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="53b45-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b45-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53b45-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="53b45-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53b45-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="53b45-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="53b45-105">The name of a method parameter.</span></span> <span data-ttu-id="53b45-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="53b45-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="53b45-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="53b45-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53b45-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53b45-108">Remarks</span></span>  

 <span data-ttu-id="53b45-109">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="53b45-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="53b45-110">El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="53b45-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="53b45-111">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="53b45-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="53b45-112">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="53b45-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="53b45-113">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="53b45-113">Object Browser.</span></span> <span data-ttu-id="53b45-114">Para obtener más información, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="53b45-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="53b45-115">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="53b45-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53b45-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53b45-116">Example</span></span>  

 <span data-ttu-id="53b45-117">En este ejemplo se usa la `<param>` etiqueta para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="53b45-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="53b45-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="53b45-118">See also</span></span>

- [<span data-ttu-id="53b45-119">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="53b45-119">XML Comment Tags</span></span>](index.md)
