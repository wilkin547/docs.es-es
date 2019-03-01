---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 6c684a674e8d6e3bf218e0131e5fac2821855456
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966377"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="24eb7-102">\<permiso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="24eb7-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="24eb7-103">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="24eb7-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24eb7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24eb7-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24eb7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24eb7-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="24eb7-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="24eb7-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="24eb7-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="24eb7-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="24eb7-108">Incluya `member` entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="24eb7-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="24eb7-109">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="24eb7-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24eb7-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24eb7-110">Remarks</span></span>  
 <span data-ttu-id="24eb7-111">Use la `<permission>` etiqueta para documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="24eb7-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="24eb7-112">Use la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="24eb7-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="24eb7-113">Compile con [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación a un archivo.</span><span class="sxs-lookup"><span data-stu-id="24eb7-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24eb7-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24eb7-114">Example</span></span>  
 <span data-ttu-id="24eb7-115">Este ejemplo se usa el `<permission>` etiquetas para describir que el <xref:System.Security.Permissions.FileIOPermission> requerido por la `ReadFile` método.</span><span class="sxs-lookup"><span data-stu-id="24eb7-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="24eb7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="24eb7-116">See also</span></span>
- [<span data-ttu-id="24eb7-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="24eb7-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
