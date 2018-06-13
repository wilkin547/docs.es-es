---
title: '&lt;permiso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 4fafebf94be350951672f01f2d17bd00d4bab69a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602000"
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="67558-102">&lt;permiso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67558-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="67558-103">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="67558-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67558-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67558-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67558-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="67558-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="67558-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="67558-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="67558-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="67558-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="67558-108">Incluya `member` entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="67558-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="67558-109">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="67558-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67558-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67558-110">Remarks</span></span>  
 <span data-ttu-id="67558-111">Use la `<permission>` etiqueta en el acceso de un miembro de un documento.</span><span class="sxs-lookup"><span data-stu-id="67558-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="67558-112">Use la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="67558-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="67558-113">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="67558-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67558-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67558-114">Example</span></span>  
 <span data-ttu-id="67558-115">Este ejemplo se utiliza la `<permission>` etiquetas para describir que el <xref:System.Security.Permissions.FileIOPermission> requeridos por la `ReadFile` método.</span><span class="sxs-lookup"><span data-stu-id="67558-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="67558-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="67558-116">See Also</span></span>  
 [<span data-ttu-id="67558-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="67558-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
