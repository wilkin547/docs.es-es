---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 7e6a96c217b038e870b4e865315766afa3b3c757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165485"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="f46f6-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="f46f6-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="f46f6-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="f46f6-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f46f6-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f46f6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f46f6-105">Methods</span></span>  
 <span data-ttu-id="f46f6-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f46f6-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f46f6-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f46f6-107">Properties</span></span>  
 <span data-ttu-id="f46f6-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="f46f6-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="f46f6-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="f46f6-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="f46f6-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f46f6-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f46f6-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="f46f6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f46f6-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="f46f6-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f46f6-113">Requirements</span></span>  
  
|<span data-ttu-id="f46f6-114">MOF</span><span class="sxs-lookup"><span data-stu-id="f46f6-114">MOF</span></span>|<span data-ttu-id="f46f6-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f46f6-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f46f6-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f46f6-116">Namespace</span></span>|<span data-ttu-id="f46f6-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f46f6-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f46f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f46f6-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
