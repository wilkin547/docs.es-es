---
title: 'Cambio importante: Kestrel: Atributos de mensaje de registro modificados'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado Kestrel: Atributos de mensaje de registro modificados'
author: scottaddie
ms.author: scaddie
ms.date: 02/01/2021
ms.openlocfilehash: 30b03c22a6c85623fec7db14b58b169f887395a0
ms.sourcegitcommit: 4df8e005c074ceb1f978f007b222fe253be2baf3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2021
ms.locfileid: "99551543"
---
# <a name="kestrel-log-message-attributes-changed"></a><span data-ttu-id="a0f7c-103">Kestrel: Atributos de mensaje de registro modificados</span><span class="sxs-lookup"><span data-stu-id="a0f7c-103">Kestrel: Log message attributes changed</span></span>

<span data-ttu-id="a0f7c-104">Los mensajes de registro de Kestrel tienen identificadores y nombres asociados.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-104">Kestrel log messages have associated IDs and names.</span></span> <span data-ttu-id="a0f7c-105">Estos atributos identifican de forma única los distintos tipos de mensajes de registro.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-105">These attributes uniquely identify different kinds of log messages.</span></span> <span data-ttu-id="a0f7c-106">Algunos de esos identificadores y nombres se han duplicado incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-106">Some of those IDs and names were incorrectly duplicated.</span></span> <span data-ttu-id="a0f7c-107">Este problema de duplicación se ha corregido en ASP.NET Core 6.0.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-107">This duplication problem is fixed in ASP.NET Core 6.0.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="a0f7c-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a0f7c-108">Version introduced</span></span>

<span data-ttu-id="a0f7c-109">6.0</span><span class="sxs-lookup"><span data-stu-id="a0f7c-109">6.0</span></span>

## <a name="old-behavior"></a><span data-ttu-id="a0f7c-110">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a0f7c-110">Old behavior</span></span>

<span data-ttu-id="a0f7c-111">En la tabla siguiente se muestra el estado de los mensajes de registro afectados antes de ASP.NET Core 6.0.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-111">The following table shows the state of the affected log messages before ASP.NET Core 6.0.</span></span>

| <span data-ttu-id="a0f7c-112">Descripción del mensaje</span><span class="sxs-lookup"><span data-stu-id="a0f7c-112">Message description</span></span>                   | <span data-ttu-id="a0f7c-113">Nombre</span><span class="sxs-lookup"><span data-stu-id="a0f7c-113">Name</span></span>                    | <span data-ttu-id="a0f7c-114">ID</span><span class="sxs-lookup"><span data-stu-id="a0f7c-114">ID</span></span> |
|---------------------------------------|-------------------------|----|
| <span data-ttu-id="a0f7c-115">Mensajes de registros de conexión cerrada HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a0f7c-115">HTTP/2 connection closed log messages</span></span> | `Http2ConnectionClosed` | <span data-ttu-id="a0f7c-116">36</span><span class="sxs-lookup"><span data-stu-id="a0f7c-116">36</span></span> |
| <span data-ttu-id="a0f7c-117">Mensajes de registros de envío del marco HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a0f7c-117">HTTP/2 frame sending log messages</span></span>     | `Http2FrameReceived`    | <span data-ttu-id="a0f7c-118">37</span><span class="sxs-lookup"><span data-stu-id="a0f7c-118">37</span></span> |

## <a name="new-behavior"></a><span data-ttu-id="a0f7c-119">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a0f7c-119">New behavior</span></span>

<span data-ttu-id="a0f7c-120">En la tabla siguiente se muestra el estado de los mensajes de registro afectados en ASP.NET Core 6.0.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-120">The following table shows the state of the affected log messages in ASP.NET Core 6.0.</span></span>

| <span data-ttu-id="a0f7c-121">Descripción del mensaje</span><span class="sxs-lookup"><span data-stu-id="a0f7c-121">Message description</span></span>                   | <span data-ttu-id="a0f7c-122">Nombre</span><span class="sxs-lookup"><span data-stu-id="a0f7c-122">Name</span></span>                    | <span data-ttu-id="a0f7c-123">ID</span><span class="sxs-lookup"><span data-stu-id="a0f7c-123">ID</span></span> |
|---------------------------------------|-------------------------|----|
| <span data-ttu-id="a0f7c-124">Mensajes de registros de conexión cerrada HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a0f7c-124">HTTP/2 connection closed log messages</span></span> | `Http2ConnectionClosed` | <span data-ttu-id="a0f7c-125">48</span><span class="sxs-lookup"><span data-stu-id="a0f7c-125">48</span></span> |
| <span data-ttu-id="a0f7c-126">Mensajes de registros de envío del marco HTTP/2</span><span class="sxs-lookup"><span data-stu-id="a0f7c-126">HTTP/2 frame sending log messages</span></span>     | `Http2FrameSending`     | <span data-ttu-id="a0f7c-127">49</span><span class="sxs-lookup"><span data-stu-id="a0f7c-127">49</span></span> |

## <a name="reason-for-change"></a><span data-ttu-id="a0f7c-128">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a0f7c-128">Reason for change</span></span>

<span data-ttu-id="a0f7c-129">Los identificadores de registro y los nombres deben ser únicos, por lo que se pueden identificar distintos tipos de mensajes.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-129">Log IDs and names should be unique so different message types can be identified.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="a0f7c-130">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a0f7c-130">Recommended action</span></span>

<span data-ttu-id="a0f7c-131">Si tiene un código o una configuración que hace referencia a los identificadores y nombres antiguos, actualice esas referencias para usar los nuevos identificadores y nombres.</span><span class="sxs-lookup"><span data-stu-id="a0f7c-131">If you have code or configuration that references the old IDs and names, update those references to use the new IDs and names.</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
