---
description: 'Más información acerca de: <param> (Visual Basic)'
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 94fe5e11d5846f7fa00eb73c1c4363990ae23b2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700297"
---
# <a name="param-visual-basic"></a><span data-ttu-id="54390-103">\<param> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54390-103">\<param> (Visual Basic)</span></span>

<span data-ttu-id="54390-104">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="54390-104">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54390-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54390-105">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="54390-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54390-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="54390-107">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="54390-107">The name of a method parameter.</span></span> <span data-ttu-id="54390-108">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="54390-108">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="54390-109">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="54390-109">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54390-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54390-110">Remarks</span></span>  

 <span data-ttu-id="54390-111">La etiqueta `<param>` debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="54390-111">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="54390-112">El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="54390-112">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="54390-113">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="54390-113">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="54390-114">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="54390-114">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="54390-115">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="54390-115">Object Browser.</span></span> <span data-ttu-id="54390-116">Para obtener más información, vea [ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="54390-116">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="54390-117">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="54390-117">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54390-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54390-118">Example</span></span>  

 <span data-ttu-id="54390-119">En este ejemplo se usa la `<param>` etiqueta para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="54390-119">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="54390-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="54390-120">See also</span></span>

- [<span data-ttu-id="54390-121">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="54390-121">XML Comment Tags</span></span>](index.md)
