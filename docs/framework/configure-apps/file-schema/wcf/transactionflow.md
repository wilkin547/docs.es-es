---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: ef3d92e07aaf4d4ba9d90e381017db104f2cc8fe
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356590"
---
# <a name="transactionflow"></a><span data-ttu-id="52eba-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="52eba-101">\<transactionFlow></span></span>
<span data-ttu-id="52eba-102">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="52eba-102">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="52eba-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="52eba-103">\<system.serviceModel></span></span>  
<span data-ttu-id="52eba-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="52eba-104">\<bindings></span></span>  
<span data-ttu-id="52eba-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="52eba-105">\<customBinding></span></span>  
<span data-ttu-id="52eba-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="52eba-106">\<binding></span></span>  
<span data-ttu-id="52eba-107">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="52eba-107">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52eba-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52eba-108">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52eba-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="52eba-109">Attributes and Elements</span></span>  
 <span data-ttu-id="52eba-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="52eba-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52eba-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="52eba-111">Attributes</span></span>  
  
|<span data-ttu-id="52eba-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="52eba-112">Attribute</span></span>|<span data-ttu-id="52eba-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="52eba-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52eba-114">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="52eba-114">transactionProtocol</span></span>|<span data-ttu-id="52eba-115">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="52eba-115">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="52eba-116">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="52eba-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="52eba-117">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="52eba-117">-   OleTransactions</span></span><br /><span data-ttu-id="52eba-118">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="52eba-118">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="52eba-119">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="52eba-119">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="52eba-120">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="52eba-120">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52eba-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="52eba-121">Child Elements</span></span>  
 <span data-ttu-id="52eba-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="52eba-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52eba-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="52eba-123">Parent Elements</span></span>  
  
|<span data-ttu-id="52eba-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="52eba-124">Element</span></span>|<span data-ttu-id="52eba-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="52eba-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52eba-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="52eba-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="52eba-127">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="52eba-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52eba-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52eba-128">Remarks</span></span>  
 <span data-ttu-id="52eba-129">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="52eba-129">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="52eba-130">Para obtener más información sobre el uso de este elemento de configuración, consulte [configuración de transacción de ServiceModel](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) y [Habilitar flujo de transacción](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="52eba-130">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="52eba-131">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="52eba-131">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="52eba-132">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="52eba-132">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52eba-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="52eba-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="52eba-134">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="52eba-134">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="52eba-135">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="52eba-135">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="52eba-136">Enlaces</span><span class="sxs-lookup"><span data-stu-id="52eba-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="52eba-137">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="52eba-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="52eba-138">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="52eba-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="52eba-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="52eba-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
