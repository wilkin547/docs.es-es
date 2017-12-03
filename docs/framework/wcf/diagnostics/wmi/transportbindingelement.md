---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2605e1a1f88434a9052059ac3ebdce429d6d6c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="transportbindingelement"></a><span data-ttu-id="f0789-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0789-102">TransportBindingElement</span></span>
<span data-ttu-id="f0789-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f0789-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0789-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0789-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f0789-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f0789-105">Methods</span></span>  
 <span data-ttu-id="f0789-106">La clase TransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f0789-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f0789-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f0789-107">Properties</span></span>  
 <span data-ttu-id="f0789-108">La clase TransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f0789-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="f0789-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="f0789-109">ManualAddressing</span></span>  
 <span data-ttu-id="f0789-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="f0789-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f0789-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f0789-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0789-112">Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f0789-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="f0789-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f0789-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="f0789-114">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="f0789-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="f0789-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f0789-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0789-116">El tamaño máximo del grupo de búferes para el enlace.</span><span class="sxs-lookup"><span data-stu-id="f0789-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="f0789-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f0789-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="f0789-118">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="f0789-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="f0789-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f0789-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0789-120">El tamaño máximo para un mensaje que es procesado por este enlace.</span><span class="sxs-lookup"><span data-stu-id="f0789-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="f0789-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="f0789-121">Scheme</span></span>  
 <span data-ttu-id="f0789-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="f0789-122">Data type: string</span></span>  
  
 <span data-ttu-id="f0789-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f0789-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f0789-124">El esquema URI para el transporte.</span><span class="sxs-lookup"><span data-stu-id="f0789-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0789-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f0789-125">Requirements</span></span>  
  
|<span data-ttu-id="f0789-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f0789-126">MOF</span></span>|<span data-ttu-id="f0789-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f0789-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f0789-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f0789-128">Namespace</span></span>|<span data-ttu-id="f0789-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0789-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0789-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0789-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
