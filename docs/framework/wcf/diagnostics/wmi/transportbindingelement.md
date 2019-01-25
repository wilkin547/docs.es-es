---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668462"
---
# <a name="transportbindingelement"></a><span data-ttu-id="fe14f-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fe14f-102">TransportBindingElement</span></span>
<span data-ttu-id="fe14f-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="fe14f-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe14f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe14f-104">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fe14f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fe14f-105">Methods</span></span>  
 <span data-ttu-id="fe14f-106">La clase TransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fe14f-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fe14f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fe14f-107">Properties</span></span>  
 <span data-ttu-id="fe14f-108">La clase TransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe14f-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="fe14f-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="fe14f-109">ManualAddressing</span></span>  
 <span data-ttu-id="fe14f-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="fe14f-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="fe14f-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fe14f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe14f-112">Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="fe14f-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="fe14f-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="fe14f-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="fe14f-114">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="fe14f-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="fe14f-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fe14f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe14f-116">El tamaño máximo del grupo de búferes para el enlace.</span><span class="sxs-lookup"><span data-stu-id="fe14f-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="fe14f-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="fe14f-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="fe14f-118">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="fe14f-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="fe14f-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fe14f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe14f-120">El tamaño máximo para un mensaje que es procesado por este enlace.</span><span class="sxs-lookup"><span data-stu-id="fe14f-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="fe14f-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="fe14f-121">Scheme</span></span>  
 <span data-ttu-id="fe14f-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="fe14f-122">Data type: string</span></span>  
  
 <span data-ttu-id="fe14f-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="fe14f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fe14f-124">El esquema URI para el transporte.</span><span class="sxs-lookup"><span data-stu-id="fe14f-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe14f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe14f-125">Requirements</span></span>  
  
|<span data-ttu-id="fe14f-126">MOF</span><span class="sxs-lookup"><span data-stu-id="fe14f-126">MOF</span></span>|<span data-ttu-id="fe14f-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fe14f-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fe14f-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fe14f-128">Namespace</span></span>|<span data-ttu-id="fe14f-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fe14f-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe14f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe14f-130">See also</span></span>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
