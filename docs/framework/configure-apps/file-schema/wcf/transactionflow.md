---
title: '&lt;transactionFlow&gt;'
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c708098676e5634281e29c17639304a1a9cf5afe
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748716"
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="520a1-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="520a1-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="520a1-103">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="520a1-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="520a1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="520a1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="520a1-105">\<enlaces ></span><span class="sxs-lookup"><span data-stu-id="520a1-105">\<bindings></span></span>  
<span data-ttu-id="520a1-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="520a1-106">\<customBinding></span></span>  
<span data-ttu-id="520a1-107">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="520a1-107">\<binding></span></span>  
<span data-ttu-id="520a1-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="520a1-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="520a1-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="520a1-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="520a1-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="520a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="520a1-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="520a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="520a1-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="520a1-112">Attributes</span></span>  
  
|<span data-ttu-id="520a1-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="520a1-113">Attribute</span></span>|<span data-ttu-id="520a1-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="520a1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="520a1-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="520a1-115">transactionProtocol</span></span>|<span data-ttu-id="520a1-116">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="520a1-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="520a1-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="520a1-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="520a1-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="520a1-118">-   OleTransactions</span></span><br /><span data-ttu-id="520a1-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="520a1-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="520a1-120">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="520a1-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="520a1-121">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="520a1-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="520a1-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="520a1-122">Child Elements</span></span>  
 <span data-ttu-id="520a1-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="520a1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="520a1-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="520a1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="520a1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="520a1-125">Element</span></span>|<span data-ttu-id="520a1-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="520a1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="520a1-127">\<enlace ></span><span class="sxs-lookup"><span data-stu-id="520a1-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="520a1-128">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="520a1-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="520a1-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="520a1-129">Remarks</span></span>  
 <span data-ttu-id="520a1-130">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un punto de conexión, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="520a1-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="520a1-131">Para obtener más información sobre el uso de este elemento de configuración, consulte [configuración de transacción de ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) y [habilitar el flujo de transacciones](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="520a1-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="520a1-132">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de extremo a extremo, se puede perder el tiempo de espera de la transacción si el extremo de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="520a1-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="520a1-133">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="520a1-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520a1-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="520a1-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="520a1-135">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="520a1-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="520a1-136">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="520a1-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="520a1-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="520a1-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="520a1-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="520a1-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="520a1-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="520a1-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="520a1-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="520a1-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
