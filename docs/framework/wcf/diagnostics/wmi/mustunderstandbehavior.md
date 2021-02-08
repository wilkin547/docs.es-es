---
description: 'Más información acerca de: MustUnderstandBehavior'
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 173548f2f3346a79bf7f53c90384db94a638a366
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803131"
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="be537-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="be537-103">MustUnderstandBehavior</span></span>

<span data-ttu-id="be537-104">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="be537-104">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be537-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be537-105">Syntax</span></span>  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="be537-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="be537-106">Methods</span></span>  

 <span data-ttu-id="be537-107">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="be537-107">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="be537-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="be537-108">Properties</span></span>  

 <span data-ttu-id="be537-109">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="be537-109">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="be537-110">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="be537-110">ValidateMustUnderstand</span></span>  

 <span data-ttu-id="be537-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="be537-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="be537-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="be537-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="be537-113">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="be537-113">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be537-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be537-114">Requirements</span></span>  
  
|<span data-ttu-id="be537-115">MOF</span><span class="sxs-lookup"><span data-stu-id="be537-115">MOF</span></span>|<span data-ttu-id="be537-116">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="be537-116">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="be537-117">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="be537-117">Namespace</span></span>|<span data-ttu-id="be537-118">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="be537-118">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be537-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="be537-119">See also</span></span>

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
