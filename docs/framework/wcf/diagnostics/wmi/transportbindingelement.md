---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: dc7a29e5911a9d0a774e36f5be8c1f3cacad69b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486622"
---
# <a name="transportbindingelement"></a><span data-ttu-id="79f1c-102">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="79f1c-102">TransportBindingElement</span></span>
<span data-ttu-id="79f1c-103">TransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="79f1c-103">TransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79f1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79f1c-104">Syntax</span></span>  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="79f1c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="79f1c-105">Methods</span></span>  
 <span data-ttu-id="79f1c-106">La clase TransportBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="79f1c-106">The TransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="79f1c-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="79f1c-107">Properties</span></span>  
 <span data-ttu-id="79f1c-108">La clase TransportBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="79f1c-108">The TransportBindingElement class has the following properties:</span></span>  
  
### <a name="manualaddressing"></a><span data-ttu-id="79f1c-109">ManualAddressing</span><span class="sxs-lookup"><span data-stu-id="79f1c-109">ManualAddressing</span></span>  
 <span data-ttu-id="79f1c-110">Tipo de datos: booleano</span><span class="sxs-lookup"><span data-stu-id="79f1c-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="79f1c-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79f1c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79f1c-112">Un valor booleano que especifica si el usuario toma el control del direccionamiento de mensajes.</span><span class="sxs-lookup"><span data-stu-id="79f1c-112">A boolean value that specifies whether the user wants to take control of message addressing.</span></span>  
  
### <a name="maxbufferpoolsize"></a><span data-ttu-id="79f1c-113">MaxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="79f1c-113">MaxBufferPoolSize</span></span>  
 <span data-ttu-id="79f1c-114">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="79f1c-114">Data type: sint64</span></span>  
  
 <span data-ttu-id="79f1c-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79f1c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79f1c-116">El tamaño máximo del grupo de búferes para el enlace.</span><span class="sxs-lookup"><span data-stu-id="79f1c-116">The maximum buffer pool size for the binding.</span></span>  
  
### <a name="maxreceivedmessagesize"></a><span data-ttu-id="79f1c-117">MaxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="79f1c-117">MaxReceivedMessageSize</span></span>  
 <span data-ttu-id="79f1c-118">Tipo de datos: sint64</span><span class="sxs-lookup"><span data-stu-id="79f1c-118">Data type: sint64</span></span>  
  
 <span data-ttu-id="79f1c-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79f1c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79f1c-120">El tamaño máximo para un mensaje que es procesado por este enlace.</span><span class="sxs-lookup"><span data-stu-id="79f1c-120">The maximum size for a message that is processed by this binding.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="79f1c-121">Scheme</span><span class="sxs-lookup"><span data-stu-id="79f1c-121">Scheme</span></span>  
 <span data-ttu-id="79f1c-122">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="79f1c-122">Data type: string</span></span>  
  
 <span data-ttu-id="79f1c-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="79f1c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="79f1c-124">El esquema URI para el transporte.</span><span class="sxs-lookup"><span data-stu-id="79f1c-124">The URI scheme for the transport.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79f1c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79f1c-125">Requirements</span></span>  
  
|<span data-ttu-id="79f1c-126">MOF</span><span class="sxs-lookup"><span data-stu-id="79f1c-126">MOF</span></span>|<span data-ttu-id="79f1c-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="79f1c-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="79f1c-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="79f1c-128">Namespace</span></span>|<span data-ttu-id="79f1c-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="79f1c-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79f1c-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="79f1c-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
