---
description: 'Más información acerca de: <transactionFlow>'
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: 8a853beaec1837606ecb96156b8ec9381fa3e07a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99773555"
---
# \<transactionFlow>

<span data-ttu-id="0bff1-102">Especifica la compatibilidad de flujo de transacción para el enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0bff1-102">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="0bff1-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0bff1-103">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0bff1-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0bff1-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0bff1-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0bff1-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0bff1-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="0bff1-106">Attributes</span></span>  
  
|<span data-ttu-id="0bff1-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="0bff1-107">Attribute</span></span>|<span data-ttu-id="0bff1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bff1-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0bff1-109">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="0bff1-109">transactionProtocol</span></span>|<span data-ttu-id="0bff1-110">Especifica el protocolo de transacción que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="0bff1-110">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="0bff1-111">Los valores válidos incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="0bff1-111">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0bff1-112">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="0bff1-112">-   OleTransactions</span></span><br /><span data-ttu-id="0bff1-113">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="0bff1-113">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="0bff1-114">El valor predeterminado es OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="0bff1-114">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="0bff1-115">Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.</span><span class="sxs-lookup"><span data-stu-id="0bff1-115">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0bff1-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0bff1-116">Child Elements</span></span>  

 <span data-ttu-id="0bff1-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0bff1-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0bff1-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0bff1-118">Parent Elements</span></span>  
  
|<span data-ttu-id="0bff1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0bff1-119">Element</span></span>|<span data-ttu-id="0bff1-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0bff1-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0bff1-121">Define todas las funcionalidades de enlace del enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="0bff1-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0bff1-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0bff1-122">Remarks</span></span>  

 <span data-ttu-id="0bff1-123">Este elemento le permite habilitar o deshabilitar el flujo de la transacción entrante en el valor de enlace de un extremo, así como especificar el formato del protocolo deseado para las transacciones entrantes.</span><span class="sxs-lookup"><span data-stu-id="0bff1-123">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="0bff1-124">Para obtener más información sobre el uso de este elemento de configuración, vea [configuración de transacciones de ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) y habilitar el flujo de [transacción](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0bff1-124">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="0bff1-125">Al utilizar el protocolo `OleTransactions` para realizar el flujo de las transacciones de punto de conexión a punto de conexión, se puede perder el tiempo de espera de la transacción si el punto de conexión de destino intenta fluir utilizando de nuevo un protocolo distinto de `OleTransactions`.</span><span class="sxs-lookup"><span data-stu-id="0bff1-125">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="0bff1-126">Esto puede producir que todos los nodos de nivel inferior después de OleTransactions alcancen el tiempo de espera más tarde de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="0bff1-126">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bff1-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bff1-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="0bff1-128">Configuración de la transacción ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0bff1-128">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="0bff1-129">Habilitar el flujo de transacciones</span><span class="sxs-lookup"><span data-stu-id="0bff1-129">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="0bff1-130">Enlaces</span><span class="sxs-lookup"><span data-stu-id="0bff1-130">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0bff1-131">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="0bff1-131">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0bff1-132">Enlaces personalizados</span><span class="sxs-lookup"><span data-stu-id="0bff1-132">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
