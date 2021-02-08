---
description: 'Más información acerca de: MtomMessageEncodingBindingElement'
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: f06e3d7266c4f7e6f9b4639f7d82941cbabb5dd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803144"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="eb27b-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb27b-103">MtomMessageEncodingBindingElement</span></span>

<span data-ttu-id="eb27b-104">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="eb27b-104">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb27b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb27b-105">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eb27b-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb27b-106">Methods</span></span>  

 <span data-ttu-id="eb27b-107">La clase MtomMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="eb27b-107">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eb27b-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="eb27b-108">Properties</span></span>  

 <span data-ttu-id="eb27b-109">La clase MtomMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="eb27b-109">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="eb27b-110">Encoding</span><span class="sxs-lookup"><span data-stu-id="eb27b-110">Encoding</span></span>  

 <span data-ttu-id="eb27b-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="eb27b-111">Data type: string</span></span>  
  
 <span data-ttu-id="eb27b-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eb27b-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb27b-113">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="eb27b-113">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="eb27b-114">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="eb27b-114">MaxReadPoolSize</span></span>  

 <span data-ttu-id="eb27b-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eb27b-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb27b-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eb27b-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb27b-117">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="eb27b-117">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="eb27b-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="eb27b-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="eb27b-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="eb27b-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="eb27b-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eb27b-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb27b-121">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="eb27b-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="eb27b-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="eb27b-122">ReaderQuotas</span></span>  

 <span data-ttu-id="eb27b-123">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="eb27b-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="eb27b-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="eb27b-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eb27b-125">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="eb27b-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb27b-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb27b-126">Requirements</span></span>  
  
|<span data-ttu-id="eb27b-127">MOF</span><span class="sxs-lookup"><span data-stu-id="eb27b-127">MOF</span></span>|<span data-ttu-id="eb27b-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eb27b-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eb27b-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="eb27b-129">Namespace</span></span>|<span data-ttu-id="eb27b-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eb27b-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb27b-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb27b-131">See also</span></span>

- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
