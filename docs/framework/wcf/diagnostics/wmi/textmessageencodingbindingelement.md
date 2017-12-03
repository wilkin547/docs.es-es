---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 966f1ae06f5d7e0dacb8b7d450463c75f783ef1f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="52c9f-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="52c9f-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="52c9f-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="52c9f-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52c9f-104">Syntax</span></span>  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="52c9f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="52c9f-105">Methods</span></span>  
 <span data-ttu-id="52c9f-106">La clase TextMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="52c9f-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="52c9f-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="52c9f-107">Properties</span></span>  
 <span data-ttu-id="52c9f-108">La clase TextMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="52c9f-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="52c9f-109">Codificación</span><span class="sxs-lookup"><span data-stu-id="52c9f-109">Encoding</span></span>  
 <span data-ttu-id="52c9f-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="52c9f-110">Data type: string</span></span>  
  
 <span data-ttu-id="52c9f-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52c9f-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52c9f-112">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="52c9f-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="52c9f-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="52c9f-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="52c9f-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="52c9f-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="52c9f-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52c9f-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52c9f-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="52c9f-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="52c9f-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="52c9f-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="52c9f-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="52c9f-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="52c9f-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52c9f-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52c9f-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="52c9f-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="52c9f-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="52c9f-121">ReaderQuotas</span></span>  
 <span data-ttu-id="52c9f-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="52c9f-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="52c9f-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="52c9f-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="52c9f-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="52c9f-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c9f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52c9f-125">Requirements</span></span>  
  
|<span data-ttu-id="52c9f-126">MOF</span><span class="sxs-lookup"><span data-stu-id="52c9f-126">MOF</span></span>|<span data-ttu-id="52c9f-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="52c9f-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="52c9f-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="52c9f-128">Namespace</span></span>|<span data-ttu-id="52c9f-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="52c9f-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52c9f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="52c9f-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
