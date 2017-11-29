---
title: '&lt;permiso&gt; (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 67e11998e43a43f92c26eb5f7daa488d288823c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="8f67e-102">&lt;permiso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f67e-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="8f67e-103">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="8f67e-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f67e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f67e-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f67e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f67e-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="8f67e-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="8f67e-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="8f67e-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="8f67e-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="8f67e-108">Incluya `member` entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="8f67e-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="8f67e-109">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="8f67e-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f67e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f67e-110">Remarks</span></span>  
 <span data-ttu-id="8f67e-111">Use la `<permission>` etiqueta en el acceso de un miembro de un documento.</span><span class="sxs-lookup"><span data-stu-id="8f67e-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="8f67e-112">Use la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="8f67e-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="8f67e-113">Compile con el parámetro [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación y generar un archivo con ellos.</span><span class="sxs-lookup"><span data-stu-id="8f67e-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f67e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f67e-114">Example</span></span>  
 <span data-ttu-id="8f67e-115">Este ejemplo se utiliza la `<permission>` etiquetas para describir que el <xref:System.Security.Permissions.FileIOPermission> requeridos por la `ReadFile` método.</span><span class="sxs-lookup"><span data-stu-id="8f67e-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8f67e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f67e-116">See Also</span></span>  
 [<span data-ttu-id="8f67e-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="8f67e-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
