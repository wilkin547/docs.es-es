---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250442"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="b3be0-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="b3be0-102">MustUnderstandBehavior</span></span>

<span data-ttu-id="b3be0-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="b3be0-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3be0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3be0-104">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b3be0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b3be0-105">Methods</span></span>  

 <span data-ttu-id="b3be0-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="b3be0-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b3be0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b3be0-107">Properties</span></span>  

 <span data-ttu-id="b3be0-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3be0-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="b3be0-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="b3be0-109">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="b3be0-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="b3be0-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b3be0-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="b3be0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b3be0-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="b3be0-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3be0-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3be0-113">Requirements</span></span>  
  
|<span data-ttu-id="b3be0-114">MOF</span><span class="sxs-lookup"><span data-stu-id="b3be0-114">MOF</span></span>|<span data-ttu-id="b3be0-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b3be0-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b3be0-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="b3be0-116">Namespace</span></span>|<span data-ttu-id="b3be0-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b3be0-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3be0-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3be0-118">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
