---
description: 'Más información acerca de: BinaryMessageEncodingBindingElement'
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e2bc711416c61ca29a93fbf75e4e734137f2b4be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757883"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="fbf65-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="fbf65-103">BinaryMessageEncodingBindingElement</span></span>

<span data-ttu-id="fbf65-104">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="fbf65-104">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf65-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbf65-105">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fbf65-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="fbf65-106">Methods</span></span>  

 <span data-ttu-id="fbf65-107">La clase BinaryMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="fbf65-107">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fbf65-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="fbf65-108">Properties</span></span>  

 <span data-ttu-id="fbf65-109">La clase BinaryMessageEncodingBindingElement tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="fbf65-109">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="fbf65-110">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="fbf65-110">MaxReadPoolSize</span></span>  

 <span data-ttu-id="fbf65-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fbf65-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="fbf65-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fbf65-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fbf65-113">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="fbf65-113">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="fbf65-114">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="fbf65-114">MaxSessionSize</span></span>  

 <span data-ttu-id="fbf65-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fbf65-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="fbf65-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fbf65-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fbf65-117">Valor que especifica el tamaño, en bytes, del búfer usado para codificar.</span><span class="sxs-lookup"><span data-stu-id="fbf65-117">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="fbf65-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="fbf65-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="fbf65-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="fbf65-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="fbf65-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fbf65-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fbf65-121">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="fbf65-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="fbf65-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fbf65-122">ReaderQuotas</span></span>  

 <span data-ttu-id="fbf65-123">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="fbf65-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="fbf65-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="fbf65-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fbf65-125">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="fbf65-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf65-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbf65-126">Requirements</span></span>  
  
|<span data-ttu-id="fbf65-127">MOF</span><span class="sxs-lookup"><span data-stu-id="fbf65-127">MOF</span></span>|<span data-ttu-id="fbf65-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="fbf65-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fbf65-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="fbf65-129">Namespace</span></span>|<span data-ttu-id="fbf65-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fbf65-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbf65-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbf65-131">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
