---
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 67c1083daa9acfd204d4de50d4e9178b25aafcf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979022"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="9f4d2-102">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f4d2-102">TextMessageEncodingBindingElement</span></span>
<span data-ttu-id="9f4d2-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="9f4d2-103">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f4d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f4d2-104">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9f4d2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9f4d2-105">Methods</span></span>  
 <span data-ttu-id="9f4d2-106">La clase TextMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-106">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9f4d2-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="9f4d2-107">Properties</span></span>  
 <span data-ttu-id="9f4d2-108">La clase TextMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="9f4d2-108">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="9f4d2-109">Codificación</span><span class="sxs-lookup"><span data-stu-id="9f4d2-109">Encoding</span></span>  
 <span data-ttu-id="9f4d2-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="9f4d2-110">Data type: string</span></span>  
  
 <span data-ttu-id="9f4d2-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="9f4d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f4d2-112">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="9f4d2-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="9f4d2-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="9f4d2-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="9f4d2-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9f4d2-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="9f4d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f4d2-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="9f4d2-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="9f4d2-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="9f4d2-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="9f4d2-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="9f4d2-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="9f4d2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f4d2-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="9f4d2-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="9f4d2-121">ReaderQuotas</span></span>  
 <span data-ttu-id="9f4d2-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="9f4d2-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="9f4d2-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="9f4d2-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f4d2-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f4d2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f4d2-125">Requirements</span></span>  
  
|<span data-ttu-id="9f4d2-126">MOF</span><span class="sxs-lookup"><span data-stu-id="9f4d2-126">MOF</span></span>|<span data-ttu-id="9f4d2-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9f4d2-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9f4d2-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="9f4d2-128">Namespace</span></span>|<span data-ttu-id="9f4d2-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9f4d2-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f4d2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f4d2-130">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
