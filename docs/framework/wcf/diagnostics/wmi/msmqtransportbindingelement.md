---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 6590c5188e4e1758987a75fbd007099703ea6bc5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250429"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="f123a-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f123a-102">MsmqTransportBindingElement</span></span>

<span data-ttu-id="f123a-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f123a-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f123a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f123a-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f123a-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f123a-105">Methods</span></span>  

 <span data-ttu-id="f123a-106">La clase MsmqTransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f123a-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f123a-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f123a-107">Properties</span></span>  

 <span data-ttu-id="f123a-108">La clase MsmqTransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f123a-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="f123a-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="f123a-109">MaxPoolSize</span></span>  

 <span data-ttu-id="f123a-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f123a-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f123a-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f123a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f123a-112">El tamaño máximo del grupo que contiene los objetos de mensaje de MSMQ internos.</span><span class="sxs-lookup"><span data-stu-id="f123a-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="f123a-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="f123a-113">QueueTransferProtocol</span></span>  

 <span data-ttu-id="f123a-114">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f123a-114">Data type: string</span></span>  
  
 <span data-ttu-id="f123a-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f123a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f123a-116">Un valor de enumeración que indica el transporte del canal de comunicación en cola que este enlace utiliza.</span><span class="sxs-lookup"><span data-stu-id="f123a-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="f123a-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="f123a-117">UseActiveDirectory</span></span>  

 <span data-ttu-id="f123a-118">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f123a-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="f123a-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f123a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f123a-120">Devuelve un valor booleano que indica si las direcciones de la cola deberían convertirse utilizando Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f123a-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f123a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f123a-121">Requirements</span></span>  
  
|<span data-ttu-id="f123a-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f123a-122">MOF</span></span>|<span data-ttu-id="f123a-123">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f123a-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f123a-124">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f123a-124">Namespace</span></span>|<span data-ttu-id="f123a-125">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f123a-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f123a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f123a-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
