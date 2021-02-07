---
description: 'Más información acerca de: <permission> (Visual Basic)'
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 7a227e97051002c834c96297d3028f08e3ed07ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700265"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="05e8e-103">\<permission> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05e8e-103">\<permission> (Visual Basic)</span></span>

<span data-ttu-id="05e8e-104">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="05e8e-104">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05e8e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05e8e-105">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="05e8e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="05e8e-106">Parameters</span></span>  

 `member`  
 <span data-ttu-id="05e8e-107">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="05e8e-107">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="05e8e-108">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="05e8e-108">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="05e8e-109">Encerrar entre comillas `member` ("").</span><span class="sxs-lookup"><span data-stu-id="05e8e-109">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="05e8e-110">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="05e8e-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05e8e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="05e8e-111">Remarks</span></span>  

 <span data-ttu-id="05e8e-112">Use la `<permission>` etiqueta para documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="05e8e-112">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="05e8e-113">Utilice la <xref:System.Security.PermissionSet> clase para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="05e8e-113">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="05e8e-114">Compile con [-doc](../../reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="05e8e-114">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e8e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05e8e-115">Example</span></span>  

 <span data-ttu-id="05e8e-116">En este ejemplo se usa la `<permission>` etiqueta para describir que el <xref:System.Security.Permissions.FileIOPermission> método requiere `ReadFile` .</span><span class="sxs-lookup"><span data-stu-id="05e8e-116">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="05e8e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e8e-117">See also</span></span>

- [<span data-ttu-id="05e8e-118">Etiquetas de comentario XML</span><span class="sxs-lookup"><span data-stu-id="05e8e-118">XML Comment Tags</span></span>](index.md)
