---
title: "Comparación de las transacciones en COM+ y ServiceModel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87e3df31060a9c71e0b2868aa34373bca221fa79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="a548d-102">Comparación de las transacciones en COM+ y ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a548d-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="a548d-103">Este tema expone cómo simular el comportamiento de un servicio transaccional de COM+ mediante los atributos [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] que proporciona el espacio de nombres <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="a548d-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="a548d-104">Emulación de COM+ mediante los atributos de ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a548d-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="a548d-105">La siguiente tabla compara la enumeración <xref:System.EnterpriseServices.TransactionOption> utilizada para crear una transacción `EnterpriseServices`, y cómo se correlacionan con los atributos [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporcionados por el espacio de nombres <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="a548d-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="a548d-106">Atributo COM+</span><span class="sxs-lookup"><span data-stu-id="a548d-106">COM+ attribute</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a548d-107"> atributos</span><span class="sxs-lookup"><span data-stu-id="a548d-107"> attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="a548d-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="a548d-108">RequiresNew</span></span>|<span data-ttu-id="a548d-109">El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span><span class="sxs-lookup"><span data-stu-id="a548d-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="a548d-110">El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="a548d-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="a548d-111">El atributo `TransactionFlow` en el elemento de enlace es `false`.</span><span class="sxs-lookup"><span data-stu-id="a548d-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="a548d-112">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="a548d-112">Required</span></span>|<span data-ttu-id="a548d-113">El valor de <xref:System.ServiceModel.TransactionFlowAttribute> está establecido en <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span><span class="sxs-lookup"><span data-stu-id="a548d-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="a548d-114">El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `true`.</span><span class="sxs-lookup"><span data-stu-id="a548d-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="a548d-115">El atributo `TransactionFlow` en el elemento de enlace es `true`.</span><span class="sxs-lookup"><span data-stu-id="a548d-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="a548d-116">Compatible</span><span class="sxs-lookup"><span data-stu-id="a548d-116">Supported</span></span>|<span data-ttu-id="a548d-117">No existe equivalente directo.</span><span class="sxs-lookup"><span data-stu-id="a548d-117">There is no direct equivalent.</span></span> <span data-ttu-id="a548d-118">En general, debería adoptar en su lugar el comportamiento especificado para `Required`.</span><span class="sxs-lookup"><span data-stu-id="a548d-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="a548d-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="a548d-119">NotSupported</span></span>|<span data-ttu-id="a548d-120">El valor de <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="a548d-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="a548d-121">El atributo `TransactionFlow` en el elemento de enlace es `false`.</span><span class="sxs-lookup"><span data-stu-id="a548d-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="a548d-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="a548d-122">Disabled</span></span>|<span data-ttu-id="a548d-123">No existe equivalente directo.</span><span class="sxs-lookup"><span data-stu-id="a548d-123">There is no direct equivalent.</span></span> <span data-ttu-id="a548d-124">En general, debería adoptar en su lugar el comportamiento especificado para `NotSupported`.</span><span class="sxs-lookup"><span data-stu-id="a548d-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
