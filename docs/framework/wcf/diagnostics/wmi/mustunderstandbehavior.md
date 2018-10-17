---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 0f3efc446104a1afff507f6e7d2cd8c01c4ed417
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371801"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="7eac5-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="7eac5-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="7eac5-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="7eac5-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eac5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7eac5-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7eac5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7eac5-105">Methods</span></span>  
 <span data-ttu-id="7eac5-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="7eac5-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7eac5-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="7eac5-107">Properties</span></span>  
 <span data-ttu-id="7eac5-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="7eac5-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="7eac5-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="7eac5-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="7eac5-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="7eac5-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7eac5-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="7eac5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7eac5-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="7eac5-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eac5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7eac5-113">Requirements</span></span>  
  
|<span data-ttu-id="7eac5-114">MOF</span><span class="sxs-lookup"><span data-stu-id="7eac5-114">MOF</span></span>|<span data-ttu-id="7eac5-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7eac5-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7eac5-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="7eac5-116">Namespace</span></span>|<span data-ttu-id="7eac5-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7eac5-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7eac5-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7eac5-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
