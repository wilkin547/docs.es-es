---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 8247dd62f4dda853487fe52f00f8f548b627c075
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399395"
---
# <a name="transactionflow"></a><span data-ttu-id="e77d0-101">\<transactionFlow></span><span class="sxs-lookup"><span data-stu-id="e77d0-101">\<transactionFlow></span></span>
<span data-ttu-id="e77d0-102">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e77d0-102">Specifies transaction flow support for the custom binding.</span></span>  
  
<span data-ttu-id="e77d0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e77d0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e77d0-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e77d0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e77d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de enlaces**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e77d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e77d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e77d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e77d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de enlace**</span><span class="sxs-lookup"><span data-stu-id="e77d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e77d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> transactionFlow**</span><span class="sxs-lookup"><span data-stu-id="e77d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e77d0-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e77d0-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e77d0-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e77d0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e77d0-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e77d0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e77d0-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="e77d0-112">Attributes</span></span>  
  
|<span data-ttu-id="e77d0-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="e77d0-113">Attribute</span></span>|<span data-ttu-id="e77d0-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e77d0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e77d0-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="e77d0-115">transactionProtocol</span></span>|<span data-ttu-id="e77d0-116">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="e77d0-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="e77d0-117">Los valores válidos son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="e77d0-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="e77d0-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="e77d0-118">-   OleTransactions</span></span><br /><span data-ttu-id="e77d0-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="e77d0-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="e77d0-120">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="e77d0-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="e77d0-121">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="e77d0-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e77d0-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e77d0-122">Child Elements</span></span>  
 <span data-ttu-id="e77d0-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e77d0-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e77d0-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e77d0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e77d0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e77d0-125">Element</span></span>|<span data-ttu-id="e77d0-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e77d0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e77d0-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="e77d0-127">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="e77d0-128">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="e77d0-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e77d0-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e77d0-129">Remarks</span></span>  
 <span data-ttu-id="e77d0-130">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="e77d0-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="e77d0-131">Para obtener más información sobre el uso de este elemento de configuración, vea [configuración de transacciones de ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) y habilitar el flujo de [transacción](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="e77d0-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e77d0-132">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="e77d0-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="e77d0-133">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="e77d0-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e77d0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e77d0-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e77d0-135">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="e77d0-135">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="e77d0-136">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="e77d0-136">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="e77d0-137">Enlaces</span><span class="sxs-lookup"><span data-stu-id="e77d0-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e77d0-138">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="e77d0-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e77d0-139">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="e77d0-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e77d0-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e77d0-140">\<customBinding></span></span>](custombinding.md)
