---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 2d1008a4308c9fda5d2291ce704d1f19205e996a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70041260"
---
# <a name="transactionflow"></a><span data-ttu-id="9d5ff-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="9d5ff-101">\<transactionFlow></span></span>
<span data-ttu-id="9d5ff-102">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="9d5ff-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9d5ff-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9d5ff-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9d5ff-104">\<bindings></span></span>  
<span data-ttu-id="9d5ff-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9d5ff-105">\<customBinding></span></span>  
<span data-ttu-id="9d5ff-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d5ff-106">\<binding></span></span>  
<span data-ttu-id="9d5ff-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="9d5ff-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d5ff-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d5ff-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d5ff-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9d5ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9d5ff-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d5ff-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d5ff-111">Attributes</span></span>  
  
|<span data-ttu-id="9d5ff-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9d5ff-112">Attribute</span></span>|<span data-ttu-id="9d5ff-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9d5ff-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d5ff-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="9d5ff-114">transactionProtocol</span></span>|<span data-ttu-id="9d5ff-115">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="9d5ff-116">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="9d5ff-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9d5ff-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="9d5ff-117">-   OleTransactions</span></span><br /><span data-ttu-id="9d5ff-118">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="9d5ff-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="9d5ff-119">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="9d5ff-120">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d5ff-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9d5ff-121">Child Elements</span></span>  
 <span data-ttu-id="9d5ff-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d5ff-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9d5ff-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9d5ff-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d5ff-124">Element</span></span>|<span data-ttu-id="9d5ff-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9d5ff-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d5ff-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="9d5ff-126">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="9d5ff-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d5ff-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d5ff-128">Remarks</span></span>  
 <span data-ttu-id="9d5ff-129">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="9d5ff-130">Para obtener más información sobre el uso de este elemento de configuración, vea [configuración de transacciones de ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) y habilitar el flujo de [transacción](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="9d5ff-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="9d5ff-131">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="9d5ff-132">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="9d5ff-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5ff-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d5ff-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9d5ff-134">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9d5ff-134">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="9d5ff-135">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="9d5ff-135">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="9d5ff-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="9d5ff-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9d5ff-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="9d5ff-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9d5ff-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="9d5ff-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9d5ff-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9d5ff-139">\<customBinding></span></span>](custombinding.md)
