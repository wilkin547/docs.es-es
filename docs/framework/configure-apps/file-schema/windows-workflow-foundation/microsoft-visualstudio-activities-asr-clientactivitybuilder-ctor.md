---
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
ms.openlocfilehash: 99f2eb9447bdf43cb57cfe86f35d2c09044ed470
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947628"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="b7bbb-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="b7bbb-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="b7bbb-103">Crea una instancia de la clase [Microsoft. VisualStudio. Activities. ASR. ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) .</span><span class="sxs-lookup"><span data-stu-id="b7bbb-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7bbb-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7bbb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b7bbb-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="b7bbb-106">Valores de parámetros</span><span class="sxs-lookup"><span data-stu-id="b7bbb-106">Parameter Values</span></span>  
 <span data-ttu-id="b7bbb-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="b7bbb-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="b7bbb-108">Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="b7bbb-109">El valor de este parámetro no debe ser **null**.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="b7bbb-110">Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="b7bbb-111">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="b7bbb-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="b7bbb-112">*configurationName*</span></span>  
  
 <span data-ttu-id="b7bbb-113">Especifica el nombre de configuración del extremo.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="b7bbb-114">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="b7bbb-115">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="b7bbb-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="b7bbb-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="b7bbb-117">Especifica el espacio de nombres de servicio para la operación.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="b7bbb-118">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="b7bbb-119">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="b7bbb-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bbb-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7bbb-120">See also</span></span>

- [<span data-ttu-id="b7bbb-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="b7bbb-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
