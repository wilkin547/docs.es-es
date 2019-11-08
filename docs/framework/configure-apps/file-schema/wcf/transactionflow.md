---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736317"
---
# <a name="transactionflow"></a><span data-ttu-id="5b467-101">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="5b467-101">\<transactionFlow></span></span>
<span data-ttu-id="5b467-102">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5b467-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="5b467-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5b467-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5b467-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5b467-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5b467-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**enlaces**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="5b467-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5b467-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding**](custombinding.md) ></span><span class="sxs-lookup"><span data-stu-id="5b467-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5b467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**enlace** ></span><span class="sxs-lookup"><span data-stu-id="5b467-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5b467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<transactionFlow >**</span><span class="sxs-lookup"><span data-stu-id="5b467-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b467-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b467-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b467-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b467-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5b467-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b467-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b467-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b467-112">Attributes</span></span>  
  
|<span data-ttu-id="5b467-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b467-113">Attribute</span></span>|<span data-ttu-id="5b467-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b467-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b467-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="5b467-115">transactionProtocol</span></span>|<span data-ttu-id="5b467-116">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="5b467-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="5b467-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="5b467-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="5b467-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="5b467-118">-   OleTransactions</span></span><br /><span data-ttu-id="5b467-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="5b467-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="5b467-120">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="5b467-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="5b467-121">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="5b467-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b467-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b467-122">Child Elements</span></span>  
 <span data-ttu-id="5b467-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5b467-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b467-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b467-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5b467-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b467-125">Element</span></span>|<span data-ttu-id="5b467-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b467-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b467-127">\<> de enlace</span><span class="sxs-lookup"><span data-stu-id="5b467-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="5b467-128">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="5b467-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b467-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b467-129">Remarks</span></span>  
 <span data-ttu-id="5b467-130">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="5b467-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="5b467-131">Para obtener más información sobre el uso de este elemento de configuración, vea [configuración de transacciones de ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) y habilitar el flujo de [transacción](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="5b467-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="5b467-132">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="5b467-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="5b467-133">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="5b467-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b467-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b467-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5b467-135">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5b467-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="5b467-136">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="5b467-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="5b467-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="5b467-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5b467-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="5b467-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5b467-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="5b467-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5b467-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5b467-140">\<customBinding></span></span>](custombinding.md)
