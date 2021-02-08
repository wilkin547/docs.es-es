---
description: 'Más información acerca de: MsmqTransportBindingElement'
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 4b6f363d979972c6ff0a2a378906feeece2ff6b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803157"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="eca67-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eca67-103">MsmqTransportBindingElement</span></span>

<span data-ttu-id="eca67-104">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="eca67-104">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca67-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eca67-105">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eca67-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="eca67-106">Methods</span></span>  

 <span data-ttu-id="eca67-107">La clase MsmqTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="eca67-107">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eca67-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="eca67-108">Properties</span></span>  

 <span data-ttu-id="eca67-109">La clase MsmqTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="eca67-109">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="eca67-110">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="eca67-110">MaxPoolSize</span></span>  

 <span data-ttu-id="eca67-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eca67-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="eca67-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eca67-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eca67-113">El tamaño máximo del grupo que contiene los objetos de mensaje de MSMQ internos.</span><span class="sxs-lookup"><span data-stu-id="eca67-113">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="eca67-114">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="eca67-114">QueueTransferProtocol</span></span>  

 <span data-ttu-id="eca67-115">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="eca67-115">Data type: string</span></span>  
  
 <span data-ttu-id="eca67-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eca67-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eca67-117">Un valor de enumeración que indica el transporte del canal de comunicación en cola que este enlace utiliza.</span><span class="sxs-lookup"><span data-stu-id="eca67-117">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="eca67-118">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="eca67-118">UseActiveDirectory</span></span>  

 <span data-ttu-id="eca67-119">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="eca67-119">Data type: boolean</span></span>  
  
 <span data-ttu-id="eca67-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eca67-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eca67-121">Devuelve un valor booleano que indica si las direcciones de la cola deberían convertirse utilizando Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eca67-121">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eca67-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eca67-122">Requirements</span></span>  
  
|<span data-ttu-id="eca67-123">MOF</span><span class="sxs-lookup"><span data-stu-id="eca67-123">MOF</span></span>|<span data-ttu-id="eca67-124">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eca67-124">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eca67-125">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="eca67-125">Namespace</span></span>|<span data-ttu-id="eca67-126">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eca67-126">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eca67-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="eca67-127">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
