---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452604"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="58c3d-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="58c3d-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="58c3d-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="58c3d-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c3d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58c3d-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="58c3d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="58c3d-105">Methods</span></span>  
 <span data-ttu-id="58c3d-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="58c3d-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="58c3d-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="58c3d-107">Properties</span></span>  
 <span data-ttu-id="58c3d-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="58c3d-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="58c3d-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="58c3d-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="58c3d-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="58c3d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="58c3d-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="58c3d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="58c3d-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="58c3d-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c3d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58c3d-113">Requirements</span></span>  
  
|<span data-ttu-id="58c3d-114">MOF</span><span class="sxs-lookup"><span data-stu-id="58c3d-114">MOF</span></span>|<span data-ttu-id="58c3d-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="58c3d-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="58c3d-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="58c3d-116">Namespace</span></span>|<span data-ttu-id="58c3d-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="58c3d-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58c3d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="58c3d-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
