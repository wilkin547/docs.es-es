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
ms.openlocfilehash: 0ce9be30182f9181bcb6449529d9b9796aadbc2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133541"
---
# <a name="microsoftvisualstudioactivitiesasrclientactivitybuilderctor"></a><span data-ttu-id="578fe-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span><span class="sxs-lookup"><span data-stu-id="578fe-102">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder..ctor</span></span>
<span data-ttu-id="578fe-103">Crea una instancia de la [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) clase.</span><span class="sxs-lookup"><span data-stu-id="578fe-103">Creates an instance of the [Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md) class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="578fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="578fe-104">Syntax</span></span>  
  
```csharp  
public ClientActivityBuilder(OperationDescription operationDescription, string configurationName, string proxyNamespace);  
```  
  
## <a name="parameters"></a><span data-ttu-id="578fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="578fe-105">Parameters</span></span>  
  
## <a name="parameter-values"></a><span data-ttu-id="578fe-106">Valores de parámetros</span><span class="sxs-lookup"><span data-stu-id="578fe-106">Parameter Values</span></span>  
 *<span data-ttu-id="578fe-107">operationDescription</span><span class="sxs-lookup"><span data-stu-id="578fe-107">operationDescription</span></span>*  
  
 <span data-ttu-id="578fe-108">Describe la operación que se va a realizar en la actividad de flujo de trabajo que se va a generar, incluidos el nombre de la operación, el tipo devuelto y la información de parámetros.</span><span class="sxs-lookup"><span data-stu-id="578fe-108">Describes the operation to be performed in the workflow activity that is to be generated, including the operation name, return type, and parameter information.</span></span> <span data-ttu-id="578fe-109">El valor de este parámetro no debe ser **null**.</span><span class="sxs-lookup"><span data-stu-id="578fe-109">The value of this parameter must not be **null**.</span></span> <span data-ttu-id="578fe-110">Debe describir una operación sincrónica que use un contrato de mensaje y tome un argumento con un mensaje.</span><span class="sxs-lookup"><span data-stu-id="578fe-110">It should describe a synchronous operation which uses a message contract and takes an argument with one message.</span></span> <span data-ttu-id="578fe-111">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="578fe-111">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 *<span data-ttu-id="578fe-112">configurationName</span><span class="sxs-lookup"><span data-stu-id="578fe-112">configurationName</span></span>*  
  
 <span data-ttu-id="578fe-113">Especifica el nombre de configuración del extremo.</span><span class="sxs-lookup"><span data-stu-id="578fe-113">Specifies the endpoint configuration name.</span></span> <span data-ttu-id="578fe-114">El valor de este parámetro no debe ser **null** o está vacío.</span><span class="sxs-lookup"><span data-stu-id="578fe-114">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="578fe-115">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="578fe-115">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
 *<span data-ttu-id="578fe-116">proxyNamespace</span><span class="sxs-lookup"><span data-stu-id="578fe-116">proxyNamespace</span></span>*  
  
 <span data-ttu-id="578fe-117">Especifica el espacio de nombres de servicio para la operación.</span><span class="sxs-lookup"><span data-stu-id="578fe-117">Specifies the service namespace for the operation.</span></span> <span data-ttu-id="578fe-118">El valor de este parámetro no debe ser **null** o está vacío.</span><span class="sxs-lookup"><span data-stu-id="578fe-118">The value of this parameter must not be either **null** or empty.</span></span> <span data-ttu-id="578fe-119">Si estas condiciones no se cumplen, el resultado del tiempo de ejecución de usar el constructor y los otros métodos de esta clase es indefinido.</span><span class="sxs-lookup"><span data-stu-id="578fe-119">If these conditions are not satisfied, the runtime result of using the constructor and the other methods of this class are undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578fe-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="578fe-120">See also</span></span>

- [<span data-ttu-id="578fe-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span><span class="sxs-lookup"><span data-stu-id="578fe-121">Microsoft.VisualStudio.Activities.Asr.ClientActivityBuilder</span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/microsoft-visualstudio-activities-asr-clientactivitybuilder.md)
