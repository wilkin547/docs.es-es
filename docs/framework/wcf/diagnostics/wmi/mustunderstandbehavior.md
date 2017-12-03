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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 40075acb2a098c98b4cd0ab35f213981c09f8486
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="mustunderstandbehavior"></a><span data-ttu-id="1ba39-102">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="1ba39-102">MustUnderstandBehavior</span></span>
<span data-ttu-id="1ba39-103">MustUnderstandBehavior</span><span class="sxs-lookup"><span data-stu-id="1ba39-103">MustUnderstandBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba39-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ba39-104">Syntax</span></span>  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1ba39-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1ba39-105">Methods</span></span>  
 <span data-ttu-id="1ba39-106">La clase MustUnderstandBehavior no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="1ba39-106">The MustUnderstandBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1ba39-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="1ba39-107">Properties</span></span>  
 <span data-ttu-id="1ba39-108">La clase MustUnderstandBehavior tiene la propiedad siguiente:</span><span class="sxs-lookup"><span data-stu-id="1ba39-108">The MustUnderstandBehavior class has the following property:</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="1ba39-109">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="1ba39-109">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="1ba39-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="1ba39-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="1ba39-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="1ba39-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ba39-112">Cuando `true`, todos los encabezados SOAP con el atributo `MustUnderstand` que no se administran provocan que el comportamiento produzca una excepción.</span><span class="sxs-lookup"><span data-stu-id="1ba39-112">When `true`, all SOAP headers with the `MustUnderstand` attribute that are not handled cause the behavior to throw an exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba39-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ba39-113">Requirements</span></span>  
  
|<span data-ttu-id="1ba39-114">MOF</span><span class="sxs-lookup"><span data-stu-id="1ba39-114">MOF</span></span>|<span data-ttu-id="1ba39-115">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="1ba39-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1ba39-116">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="1ba39-116">Namespace</span></span>|<span data-ttu-id="1ba39-117">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1ba39-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ba39-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba39-118">See Also</span></span>  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>
