---
title: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor
api_location: Microsoft.VisualStudio.Activities.dll
api_type: Assembly
ms.assetid: 6b44b13c-7a23-4df2-8f9f-45e2b1430002
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8d9e9bfb0967b6c41a3df0015bdd6b4101e0c06
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="63155-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="63155-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="63155-103">Crea una instancia de la [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) clase.</span><span class="sxs-lookup"><span data-stu-id="63155-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63155-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63155-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63155-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63155-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="63155-106">Valores de parámetros</span><span class="sxs-lookup"><span data-stu-id="63155-106">Parameter Values</span></span>  
 <span data-ttu-id="63155-107">*operationDescription*</span><span class="sxs-lookup"><span data-stu-id="63155-107">*operationDescription*</span></span>  
  
 <span data-ttu-id="63155-108">Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="63155-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="63155-109">El valor de este parámetro no debe ser **null**.</span><span class="sxs-lookup"><span data-stu-id="63155-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="63155-110">Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje.</span><span class="sxs-lookup"><span data-stu-id="63155-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="63155-111">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="63155-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="63155-112">*configurationName*</span><span class="sxs-lookup"><span data-stu-id="63155-112">*configurationName*</span></span>  
  
 <span data-ttu-id="63155-113">Especifica el nombre de configuración del extremo.</span><span class="sxs-lookup"><span data-stu-id="63155-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="63155-114">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="63155-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="63155-115">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="63155-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 <span data-ttu-id="63155-116">*proxyNamespace*</span><span class="sxs-lookup"><span data-stu-id="63155-116">*proxyNamespace*</span></span>  
  
 <span data-ttu-id="63155-117">Especifica el espacio de nombres de servicio para la operación.</span><span class="sxs-lookup"><span data-stu-id="63155-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="63155-118">El valor de este parámetro no debe ser **null** ni estar vacío.</span><span class="sxs-lookup"><span data-stu-id="63155-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="63155-119">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="63155-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63155-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="63155-120">See Also</span></span>  
 [<span data-ttu-id="63155-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="63155-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
