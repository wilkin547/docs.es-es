---
description: 'Más información sobre: TransportBindingElement'
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: de08feaf8abec3a0dfee97e92d68d5223cd0de44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757116"
---
# <a name="transportbindingelement"></a><span data-ttu-id="45080-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="45080-103">TransportBindingElement</span></span>

<span data-ttu-id="45080-104">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="45080-104">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45080-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45080-105">Syntax</span></span>  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="45080-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="45080-106">Methods</span></span>  

 <span data-ttu-id="45080-107">La clase TransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="45080-107">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="45080-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="45080-108">Properties</span></span>  

 <span data-ttu-id="45080-109">La clase TransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="45080-109">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="45080-110">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="45080-110">ManualAddressing</span></span>  

 <span data-ttu-id="45080-111">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="45080-111">Data type: boolean</span></span>  
  
 <span data-ttu-id="45080-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="45080-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45080-113">Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="45080-113">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="45080-114">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="45080-114">MaxBufferPoolSize</span></span>  

 <span data-ttu-id="45080-115">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="45080-115">Data type: sint64</span></span>  
  
 <span data-ttu-id="45080-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="45080-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45080-117">El tamaño máximo del grupo de búferes para el enlace.</span><span class="sxs-lookup"><span data-stu-id="45080-117">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="45080-118">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="45080-118">MaxReceivedMessageSize</span></span>  

 <span data-ttu-id="45080-119">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="45080-119">Data type: sint64</span></span>  
  
 <span data-ttu-id="45080-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="45080-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45080-121">El tamaño máximo para un mensaje que es procesado por este enlace.</span><span class="sxs-lookup"><span data-stu-id="45080-121">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="45080-122">Scheme</span><span class="sxs-lookup"><span data-stu-id="45080-122">Scheme</span></span>  

 <span data-ttu-id="45080-123">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="45080-123">Data type: string</span></span>  
  
 <span data-ttu-id="45080-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="45080-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="45080-125">El esquema URI para el transporte.</span><span class="sxs-lookup"><span data-stu-id="45080-125">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45080-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45080-126">Requirements</span></span>  
  
|<span data-ttu-id="45080-127">MOF</span><span class="sxs-lookup"><span data-stu-id="45080-127">MOF</span></span>|<span data-ttu-id="45080-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="45080-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="45080-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="45080-129">Namespace</span></span>|<span data-ttu-id="45080-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="45080-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45080-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="45080-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TransportBindingElement>
