---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: f5bcd142fb2b032ea179bcbba68fee53b98d2d77
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736317"
---
# \<transactionFlow>
<span data-ttu-id="dbcee-101">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbcee-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="dbcee-102">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbcee-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbcee-103">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dbcee-103">Attributes and Elements</span></span>  
 <span data-ttu-id="dbcee-104">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dbcee-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbcee-105">Atributos</span><span class="sxs-lookup"><span data-stu-id="dbcee-105">Attributes</span></span>  
  
|<span data-ttu-id="dbcee-106">Atributo</span><span class="sxs-lookup"><span data-stu-id="dbcee-106">Attribute</span></span>|<span data-ttu-id="dbcee-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbcee-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dbcee-108">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="dbcee-108">transactionProtocol</span></span>|<span data-ttu-id="dbcee-109">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="dbcee-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="dbcee-110">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="dbcee-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dbcee-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="dbcee-111">-   OleTransactions</span></span><br /><span data-ttu-id="dbcee-112">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="dbcee-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="dbcee-113">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="dbcee-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="dbcee-114">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="dbcee-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbcee-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dbcee-115">Child Elements</span></span>  
 <span data-ttu-id="dbcee-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dbcee-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbcee-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dbcee-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dbcee-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="dbcee-118">Element</span></span>|<span data-ttu-id="dbcee-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbcee-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="dbcee-120">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbcee-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbcee-121">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbcee-121">Remarks</span></span>  
 <span data-ttu-id="dbcee-122">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="dbcee-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="dbcee-123">Para obtener más información sobre el uso de este elemento de configuración, vea [configuración de transacciones de ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) y habilitar el flujo de [transacción](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="dbcee-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="dbcee-124">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="dbcee-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="dbcee-125">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="dbcee-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbcee-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbcee-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dbcee-127">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dbcee-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="dbcee-128">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="dbcee-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="dbcee-129">Enlaces</span><span class="sxs-lookup"><span data-stu-id="dbcee-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dbcee-130">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="dbcee-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dbcee-131">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="dbcee-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
