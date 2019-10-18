---
title: <permission> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 904d573514bf35b773d47321b7fd3b6a86e90262
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524702"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="805c5-102">\<permission > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="805c5-102">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="805c5-103">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="805c5-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="805c5-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="805c5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="805c5-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="805c5-106">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="805c5-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="805c5-107">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="805c5-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="805c5-108">Escriba `member` entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="805c5-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="805c5-109">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="805c5-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="805c5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="805c5-110">Remarks</span></span>  
 <span data-ttu-id="805c5-111">Use la etiqueta `<permission>` para documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="805c5-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="805c5-112">Utilice la clase <xref:System.Security.PermissionSet> para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="805c5-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="805c5-113">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="805c5-113">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="805c5-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="805c5-114">Example</span></span>  
 <span data-ttu-id="805c5-115">En este ejemplo se usa la etiqueta `<permission>` para describir que el método `ReadFile` requiere la <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="805c5-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="805c5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="805c5-116">See also</span></span>

- [<span data-ttu-id="805c5-117">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="805c5-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
