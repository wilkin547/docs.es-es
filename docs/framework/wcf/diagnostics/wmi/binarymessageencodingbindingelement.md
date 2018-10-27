---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: 326fe6a7ca8dc5dba0dd64b1c5fc97cec49279c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180892"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="2e503-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="2e503-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="2e503-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="2e503-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e503-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e503-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2e503-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e503-105">Methods</span></span>  
 <span data-ttu-id="2e503-106">La clase BinaryMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="2e503-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2e503-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="2e503-107">Properties</span></span>  
 <span data-ttu-id="2e503-108">La clase BinaryMessageEncodingBindingElement tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="2e503-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="2e503-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="2e503-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="2e503-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="2e503-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e503-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e503-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e503-112">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="2e503-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="2e503-113">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="2e503-113">MaxSessionSize</span></span>  
 <span data-ttu-id="2e503-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="2e503-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e503-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e503-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e503-116">Valor que especifica el tamaño, en bytes, del búfer usado para codificar.</span><span class="sxs-lookup"><span data-stu-id="2e503-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="2e503-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="2e503-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="2e503-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="2e503-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="2e503-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e503-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e503-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="2e503-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="2e503-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2e503-121">ReaderQuotas</span></span>  
 <span data-ttu-id="2e503-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="2e503-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="2e503-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="2e503-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2e503-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="2e503-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e503-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e503-125">Requirements</span></span>  
  
|<span data-ttu-id="2e503-126">MOF</span><span class="sxs-lookup"><span data-stu-id="2e503-126">MOF</span></span>|<span data-ttu-id="2e503-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="2e503-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2e503-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="2e503-128">Namespace</span></span>|<span data-ttu-id="2e503-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2e503-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e503-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e503-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
