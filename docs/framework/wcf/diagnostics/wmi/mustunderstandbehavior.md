---
title: MustUnderstandBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dca98f1d8d5f868285ecf11c01122f795ee6cfd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="4d6ab-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="4d6ab-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="4d6ab-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="4d6ab-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d6ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d6ab-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4d6ab-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4d6ab-105">Methods</span></span>  
 <span data-ttu-id="4d6ab-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="4d6ab-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d6ab-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4d6ab-107">Properties</span></span>  
 <span data-ttu-id="4d6ab-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="4d6ab-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="4d6ab-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="4d6ab-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="4d6ab-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="4d6ab-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d6ab-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="4d6ab-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d6ab-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="4d6ab-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d6ab-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d6ab-113">Requirements</span></span>  
  
|<span data-ttu-id="4d6ab-114">MOF</span><span class="sxs-lookup"><span data-stu-id="4d6ab-114">MOF</span></span>|<span data-ttu-id="4d6ab-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4d6ab-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4d6ab-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="4d6ab-116">Namespace</span></span>|<span data-ttu-id="4d6ab-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4d6ab-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4d6ab-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d6ab-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
