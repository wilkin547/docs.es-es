---
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
ms.openlocfilehash: 9f1f852c0bd82299fd40afe66a5f90cd7c0335cf
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215506"
---
# <a name="messagebodytostring-method"></a><span data-ttu-id="141d9-102">Message. BodyToString (método)</span><span class="sxs-lookup"><span data-stu-id="141d9-102">Message.BodyToString Method</span></span>

<span data-ttu-id="141d9-103">Convierte el cuerpo del mensaje en una cadena mediante una llamada al método <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="141d9-103">Converts the message body into a string by calling the <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void BodyToString(XmlDictionaryWriter writer);
```

## <a name="parameters"></a><span data-ttu-id="141d9-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="141d9-104">Parameters</span></span>

- <span data-ttu-id="141d9-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="141d9-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="141d9-106">Escritor que se utiliza para convertir el cuerpo del mensaje en una cadena.</span><span class="sxs-lookup"><span data-stu-id="141d9-106">The writer that is used to convert the message body to a string.</span></span>

## <a name="remarks"></a><span data-ttu-id="141d9-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="141d9-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="141d9-108">El método `Message.BodyToString` es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="141d9-108">The `Message.BodyToString` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="141d9-109">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="141d9-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="141d9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="141d9-110">Requirements</span></span>

<span data-ttu-id="141d9-111">**Espacio de nombres:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="141d9-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="141d9-112">**Ensamblado:** System. ServiceModel. dll</span><span class="sxs-lookup"><span data-stu-id="141d9-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="141d9-113">**.NET Framework versiones:** Disponible desde 3,0.</span><span class="sxs-lookup"><span data-stu-id="141d9-113">**.NET Framework versions:** Available since 3.0.</span></span>
