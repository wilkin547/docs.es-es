---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: d325d5f9fbfd132630cf280653be214a267a7a80
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400065"
---
# <a name="param-visual-basic"></a><span data-ttu-id="d73a6-101">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d73a6-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="d73a6-102">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="d73a6-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d73a6-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d73a6-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d73a6-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d73a6-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d73a6-105">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="d73a6-105">The name of a method parameter.</span></span> <span data-ttu-id="d73a6-106">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="d73a6-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d73a6-107">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="d73a6-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d73a6-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d73a6-108">Remarks</span></span>  
 <span data-ttu-id="d73a6-109">La `<param>` etiqueta debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="d73a6-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="d73a6-110">El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="d73a6-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="d73a6-111">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="d73a6-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="d73a6-112">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="d73a6-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="d73a6-113">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="d73a6-113">Object Browser.</span></span> <span data-ttu-id="d73a6-114">Para obtener más información, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="d73a6-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="d73a6-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación en un archivo.</span><span class="sxs-lookup"><span data-stu-id="d73a6-115">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d73a6-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d73a6-116">Example</span></span>  
 <span data-ttu-id="d73a6-117">En este ejemplo se usa la `<param>` etiqueta para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="d73a6-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d73a6-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d73a6-118">See also</span></span>

- [<span data-ttu-id="d73a6-119">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="d73a6-119">XML Comment Tags</span></span>](index.md)
