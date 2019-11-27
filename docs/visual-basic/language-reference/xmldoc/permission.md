---
title: <permission>
ms.date: 07/20/2015
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
ms.openlocfilehash: 71b00b669804e644d1171480192b9d55455bdf53
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352263"
---
# <a name="permission-visual-basic"></a><span data-ttu-id="dc69f-101">\<> de permisos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc69f-101">\<permission> (Visual Basic)</span></span>
<span data-ttu-id="dc69f-102">Especifica un permiso necesario para el miembro.</span><span class="sxs-lookup"><span data-stu-id="dc69f-102">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc69f-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc69f-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc69f-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc69f-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="dc69f-105">Referencia a un miembro o campo al cual se puede llamar desde el entorno de compilación actual.</span><span class="sxs-lookup"><span data-stu-id="dc69f-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="dc69f-106">El compilador comprueba si el elemento de código dado existe y traduce `member` al nombre de elemento canónico en la salida XML.</span><span class="sxs-lookup"><span data-stu-id="dc69f-106">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="dc69f-107">Escriba `member` entre comillas ("").</span><span class="sxs-lookup"><span data-stu-id="dc69f-107">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="dc69f-108">Descripción del acceso al miembro.</span><span class="sxs-lookup"><span data-stu-id="dc69f-108">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc69f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc69f-109">Remarks</span></span>  
 <span data-ttu-id="dc69f-110">Use la etiqueta `<permission>` para documentar el acceso de un miembro.</span><span class="sxs-lookup"><span data-stu-id="dc69f-110">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="dc69f-111">Utilice la clase <xref:System.Security.PermissionSet> para especificar el acceso a un miembro.</span><span class="sxs-lookup"><span data-stu-id="dc69f-111">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="dc69f-112">Compile con [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) para procesar los comentarios de documentación de un archivo.</span><span class="sxs-lookup"><span data-stu-id="dc69f-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc69f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc69f-113">Example</span></span>  
 <span data-ttu-id="dc69f-114">En este ejemplo se usa la etiqueta `<permission>` para describir que el método `ReadFile` requiere la <xref:System.Security.Permissions.FileIOPermission>.</span><span class="sxs-lookup"><span data-stu-id="dc69f-114">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="dc69f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc69f-115">See also</span></span>

- [<span data-ttu-id="dc69f-116">Etiquetas XML para comentarios</span><span class="sxs-lookup"><span data-stu-id="dc69f-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
