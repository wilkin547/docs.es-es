---
title: '&lt;param&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 09c7473cd88a701d8e46251be9b1c268c2dc8805
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="aa4d6-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa4d6-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="aa4d6-103">Define un nombre de parámetro y una descripción.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa4d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa4d6-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa4d6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa4d6-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="aa4d6-106">Nombre de un parámetro de método.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-106">The name of a method parameter.</span></span> <span data-ttu-id="aa4d6-107">Ponga el nombre entre comillas dobles (" ").</span><span class="sxs-lookup"><span data-stu-id="aa4d6-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="aa4d6-108">Descripción del parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa4d6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa4d6-109">Remarks</span></span>  
 <span data-ttu-id="aa4d6-110">La `<param>` etiqueta debe usarse en el comentario de una declaración de método para describir uno de los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="aa4d6-111">El texto de la `<param>` etiqueta aparecerá en las siguientes ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="aa4d6-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="aa4d6-112">Información de parámetros de IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="aa4d6-113">Para obtener más información, vea [Usar IntelliSense](/visualstudio/ide/using-intellisense).</span><span class="sxs-lookup"><span data-stu-id="aa4d6-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="aa4d6-114">Examinador de objetos.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-114">Object Browser.</span></span> <span data-ttu-id="aa4d6-115">Para obtener más información, vea [Ver la estructura del código](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="aa4d6-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="aa4d6-116">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa4d6-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa4d6-117">Example</span></span>  
 <span data-ttu-id="aa4d6-118">Este ejemplo se utiliza la `<param>` etiquetas para describir el `id` parámetro.</span><span class="sxs-lookup"><span data-stu-id="aa4d6-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="aa4d6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa4d6-119">See Also</span></span>  
 [<span data-ttu-id="aa4d6-120">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="aa4d6-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
