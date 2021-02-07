---
description: 'Más información acerca de: Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder.. ctor'
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.date: 03/30/2017
ms.topic: reference
api_name:
- Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location:
- Microsoft.VisualStudio.Activities.dll
api_type:
- Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
ms.openlocfilehash: 1a1b436c2b15fdf07f924aa0db2a13598422e988
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739994"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="febd9-103">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="febd9-103">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>

<span data-ttu-id="febd9-104">Crea una instancia de la clase [Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .</span><span class="sxs-lookup"><span data-stu-id="febd9-104">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febd9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="febd9-105">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="febd9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="febd9-106">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="febd9-107">Valores de parámetros</span><span class="sxs-lookup"><span data-stu-id="febd9-107">Parameter Values</span></span>  

 <span data-ttu-id="febd9-108">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="febd9-108">*operationDescription*</span></span>  
  
 <span data-ttu-id="febd9-109">Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="febd9-109">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="febd9-110">El valor de este parámetro no debe ser **null**.</span><span class="sxs-lookup"><span data-stu-id="febd9-110">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="febd9-111">Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje.</span><span class="sxs-lookup"><span data-stu-id="febd9-111">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="febd9-112">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="febd9-112">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="febd9-113">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="febd9-113">*configurationName*</span></span>  
  
 <span data-ttu-id="febd9-114">Especifica el nombre de configuración del extremo.</span><span class="sxs-lookup"><span data-stu-id="febd9-114">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="febd9-115">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="febd9-115">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="febd9-116">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="febd9-116">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="febd9-117">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="febd9-117">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="febd9-118">Especifica el espacio de nombres de servicio para la operación.</span><span class="sxs-lookup"><span data-stu-id="febd9-118">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="febd9-119">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="febd9-119">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="febd9-120">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="febd9-120">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febd9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="febd9-121">See also</span></span>

- [<span data-ttu-id="febd9-122">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="febd9-122">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
