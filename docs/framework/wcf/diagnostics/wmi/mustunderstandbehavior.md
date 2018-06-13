---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 14150a992130e9ed4734c950d4ed92f1bbd3206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485562"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="fb275-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="fb275-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="fb275-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="fb275-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb275-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb275-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fb275-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fb275-105">Methods</span></span>  
 <span data-ttu-id="fb275-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fb275-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fb275-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fb275-107">Properties</span></span>  
 <span data-ttu-id="fb275-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb275-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="fb275-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="fb275-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="fb275-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fb275-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fb275-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fb275-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fb275-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="fb275-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb275-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb275-113">Requirements</span></span>  
  
|<span data-ttu-id="fb275-114">MOF</span><span class="sxs-lookup"><span data-stu-id="fb275-114">MOF</span></span>|<span data-ttu-id="fb275-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fb275-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fb275-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fb275-116">Namespace</span></span>|<span data-ttu-id="fb275-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fb275-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fb275-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb275-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
