---
title: BinaryMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 45f80b9ac7ca052ea3a8d7d89b35413b167eacfa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="d018b-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d018b-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="d018b-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="d018b-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d018b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d018b-104">Syntax</span></span>  
  
```  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d018b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d018b-105">Methods</span></span>  
 <span data-ttu-id="d018b-106">La clase BinaryMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="d018b-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d018b-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="d018b-107">Properties</span></span>  
 <span data-ttu-id="d018b-108">La clase BinaryMessageEncodingBindingElement tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="d018b-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="d018b-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="d018b-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="d018b-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d018b-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="d018b-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d018b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d018b-112">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="d018b-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="d018b-113">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="d018b-113">MaxSessionSize</span></span>  
 <span data-ttu-id="d018b-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d018b-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="d018b-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d018b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d018b-116">Valor que especifica el tamaño, en bytes, del búfer usado para codificar.</span><span class="sxs-lookup"><span data-stu-id="d018b-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="d018b-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="d018b-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="d018b-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="d018b-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="d018b-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d018b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d018b-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="d018b-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="d018b-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d018b-121">ReaderQuotas</span></span>  
 <span data-ttu-id="d018b-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="d018b-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="d018b-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="d018b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d018b-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="d018b-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d018b-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d018b-125">Requirements</span></span>  
  
|<span data-ttu-id="d018b-126">MOF</span><span class="sxs-lookup"><span data-stu-id="d018b-126">MOF</span></span>|<span data-ttu-id="d018b-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="d018b-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d018b-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="d018b-128">Namespace</span></span>|<span data-ttu-id="d018b-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d018b-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d018b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="d018b-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
