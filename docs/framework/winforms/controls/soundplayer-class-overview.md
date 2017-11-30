---
title: "Información general sobre la clase SoundPlayer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b6df44df3582ed806d338e2d4565c5c11f69ce21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="6329c-102">Información general sobre la clase SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="6329c-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="6329c-103">La clase <xref:System.Media.SoundPlayer> le permite incluir con facilidad sonidos en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6329c-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="6329c-104">La <xref:System.Media.SoundPlayer> clase puede reproducir archivos de sonido en el formato .wav, desde un recurso o desde ubicaciones HTTP o UNC.</span><span class="sxs-lookup"><span data-stu-id="6329c-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="6329c-105">Además, la <xref:System.Media.SoundPlayer> clase le permite cargar o reproducir sonidos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="6329c-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="6329c-106">También puede utilizar la clase <xref:System.Media.SystemSounds> para reproducir sonidos de sistema comunes, incluso un bip. </span><span class="sxs-lookup"><span data-stu-id="6329c-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="6329c-107">Propiedades, métodos y eventos de uso común</span><span class="sxs-lookup"><span data-stu-id="6329c-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="6329c-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="6329c-108">Name</span></span>|<span data-ttu-id="6329c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6329c-109">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6329c-110">Propiedad <xref:System.Media.SoundPlayer.SoundLocation%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-110"><xref:System.Media.SoundPlayer.SoundLocation%2A> property</span></span>|<span data-ttu-id="6329c-111">Ruta de acceso del archivo o dirección web del sonido.</span><span class="sxs-lookup"><span data-stu-id="6329c-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="6329c-112">Los valores admitidos pueden ser UNC o HTTP.</span><span class="sxs-lookup"><span data-stu-id="6329c-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<span data-ttu-id="6329c-113">Propiedad <xref:System.Media.SoundPlayer.LoadTimeout%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-113"><xref:System.Media.SoundPlayer.LoadTimeout%2A> property</span></span>|<span data-ttu-id="6329c-114">Número de milisegundos que el programa esperará para cargar un sonido antes de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="6329c-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="6329c-115">El valor predeterminado es 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="6329c-115">The default is 10 seconds.</span></span>|  
|<span data-ttu-id="6329c-116">Propiedad <xref:System.Media.SoundPlayer.IsLoadCompleted%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-116"><xref:System.Media.SoundPlayer.IsLoadCompleted%2A> property</span></span>|<span data-ttu-id="6329c-117">Valor booleano que indica si el sonido finalizó la carga.</span><span class="sxs-lookup"><span data-stu-id="6329c-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<span data-ttu-id="6329c-118">Método <xref:System.Media.SoundPlayer.Load%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-118"><xref:System.Media.SoundPlayer.Load%2A> method</span></span>|<span data-ttu-id="6329c-119">Carga un sonido de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="6329c-119">Loads a sound synchronously.</span></span>|  
|<span data-ttu-id="6329c-120">Método <xref:System.Media.SoundPlayer.LoadAsync%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-120"><xref:System.Media.SoundPlayer.LoadAsync%2A> method</span></span>|<span data-ttu-id="6329c-121">Comienza a cargar un sonido de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="6329c-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="6329c-122">Una vez completada la carga, genera el <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> eventos.</span><span class="sxs-lookup"><span data-stu-id="6329c-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<span data-ttu-id="6329c-123">Método <xref:System.Media.SoundPlayer.Play%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-123"><xref:System.Media.SoundPlayer.Play%2A> method</span></span>|<span data-ttu-id="6329c-124">Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="6329c-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<span data-ttu-id="6329c-125">Método <xref:System.Media.SoundPlayer.PlaySync%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-125"><xref:System.Media.SoundPlayer.PlaySync%2A> method</span></span>|<span data-ttu-id="6329c-126">Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="6329c-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<span data-ttu-id="6329c-127">Método <xref:System.Media.SoundPlayer.Stop%2A></span><span class="sxs-lookup"><span data-stu-id="6329c-127"><xref:System.Media.SoundPlayer.Stop%2A> method</span></span>|<span data-ttu-id="6329c-128">Detiene cualquier sonido que se esté reproduciendo.</span><span class="sxs-lookup"><span data-stu-id="6329c-128">Stops any sound currently playing.</span></span>|  
|<span data-ttu-id="6329c-129">Evento <xref:System.Media.SoundPlayer.LoadCompleted></span><span class="sxs-lookup"><span data-stu-id="6329c-129"><xref:System.Media.SoundPlayer.LoadCompleted> event</span></span>|<span data-ttu-id="6329c-130">Se genera después de que se intente cargar un sonido.</span><span class="sxs-lookup"><span data-stu-id="6329c-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6329c-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6329c-131">See Also</span></span>  
 <xref:System.Media.SoundPlayer>  
 <xref:System.Media.SystemSounds>
