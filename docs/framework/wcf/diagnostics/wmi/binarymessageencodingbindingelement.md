---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768064"
---
# <a name="binarymessageencodingbindingelement"></a><span data-ttu-id="87af8-102">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="87af8-102">BinaryMessageEncodingBindingElement</span></span>
<span data-ttu-id="87af8-103">BinaryMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="87af8-103">BinaryMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87af8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87af8-104">Syntax</span></span>  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="87af8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="87af8-105">Methods</span></span>  
 <span data-ttu-id="87af8-106">La clase BinaryMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="87af8-106">The BinaryMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="87af8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="87af8-107">Properties</span></span>  
 <span data-ttu-id="87af8-108">La clase BinaryMessageEncodingBindingElement tiene las propiedades siguientes.</span><span class="sxs-lookup"><span data-stu-id="87af8-108">The BinaryMessageEncodingBindingElement class has the following properties.</span></span>  
  
## <a name="maxreadpoolsize"></a><span data-ttu-id="87af8-109">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="87af8-109">MaxReadPoolSize</span></span>  
 <span data-ttu-id="87af8-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="87af8-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="87af8-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="87af8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87af8-112">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="87af8-112">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
## <a name="maxsessionsize"></a><span data-ttu-id="87af8-113">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="87af8-113">MaxSessionSize</span></span>  
 <span data-ttu-id="87af8-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="87af8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="87af8-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="87af8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87af8-116">Valor que especifica el tamaño, en bytes, del búfer usado para codificar.</span><span class="sxs-lookup"><span data-stu-id="87af8-116">A value that specifies the size, in bytes, of the buffer used for encoding.</span></span>  
  
## <a name="maxwritepoolsize"></a><span data-ttu-id="87af8-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="87af8-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="87af8-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="87af8-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="87af8-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="87af8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87af8-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="87af8-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
## <a name="readerquotas"></a><span data-ttu-id="87af8-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="87af8-121">ReaderQuotas</span></span>  
 <span data-ttu-id="87af8-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="87af8-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="87af8-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="87af8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="87af8-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="87af8-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87af8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="87af8-125">Requirements</span></span>  
  
|<span data-ttu-id="87af8-126">MOF</span><span class="sxs-lookup"><span data-stu-id="87af8-126">MOF</span></span>|<span data-ttu-id="87af8-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="87af8-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="87af8-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="87af8-128">Namespace</span></span>|<span data-ttu-id="87af8-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="87af8-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87af8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="87af8-130">See also</span></span>

- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
