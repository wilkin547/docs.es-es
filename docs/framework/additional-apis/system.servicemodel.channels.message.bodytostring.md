---
description: 'Más información sobre: Message. BodyToString (método)'
title: Método Message. BodyToString (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.BodyToString
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: babcd881d191ff46b98e9999c4ff04166479a68d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699381"
---
# <a name="messagebodytostring-method"></a><span data-ttu-id="0f2c4-103">Message. BodyToString (método)</span><span class="sxs-lookup"><span data-stu-id="0f2c4-103">Message.BodyToString Method</span></span>

<span data-ttu-id="0f2c4-104">Convierte el cuerpo del mensaje en una cadena mediante una llamada al <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="0f2c4-104">Converts the message body into a string by calling the <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a><span data-ttu-id="0f2c4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f2c4-105">Parameters</span></span>

- <span data-ttu-id="0f2c4-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="0f2c4-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="0f2c4-107">Escritor que se utiliza para convertir el cuerpo del mensaje en una cadena.</span><span class="sxs-lookup"><span data-stu-id="0f2c4-107">The writer that is used to convert the message body to a string.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f2c4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f2c4-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="0f2c4-109">El `Message.BodyToString` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="0f2c4-109">The `Message.BodyToString` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="0f2c4-110">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="0f2c4-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f2c4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f2c4-111">Requirements</span></span>

<span data-ttu-id="0f2c4-112">**Espacio de nombres:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="0f2c4-112">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="0f2c4-113">**Ensamblado:** System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="0f2c4-113">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="0f2c4-114">**.NET Framework versiones:** Disponible desde 3,0.</span><span class="sxs-lookup"><span data-stu-id="0f2c4-114">**.NET Framework versions:** Available since 3.0.</span></span>
