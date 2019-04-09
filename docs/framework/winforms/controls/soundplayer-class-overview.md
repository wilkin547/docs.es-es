---
title: Información general sobre la clase SoundPlayer
ms.date: 03/30/2017
helpviewer_keywords:
- playing sounds [Windows Forms], SoundPlayer class
- SoundPlayer class [Windows Forms], about SoundPlayer class
- sounds [Windows Forms], playing
ms.assetid: fcebb938-62b9-4677-9cbe-6465bc863e22
ms.openlocfilehash: 3ff23cbfa78b803d4526e7a7c389fd5d458a967c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195012"
---
# <a name="soundplayer-class-overview"></a><span data-ttu-id="eadbb-102">Información general sobre la clase SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="eadbb-102">SoundPlayer Class Overview</span></span>
<span data-ttu-id="eadbb-103">La clase <xref:System.Media.SoundPlayer> le permite incluir con facilidad sonidos en las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="eadbb-103">The <xref:System.Media.SoundPlayer> class enables you to easily include sounds in your applications.</span></span>  
  
 <span data-ttu-id="eadbb-104">La <xref:System.Media.SoundPlayer> clase puede reproducir archivos de sonido en formato .wav desde un recurso o desde ubicaciones HTTP o UNC.</span><span class="sxs-lookup"><span data-stu-id="eadbb-104">The <xref:System.Media.SoundPlayer> class can play sound files in the .wav format, either from a resource or from UNC or HTTP locations.</span></span> <span data-ttu-id="eadbb-105">Además, el <xref:System.Media.SoundPlayer> clase le permite cargar o reproducir sonidos de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="eadbb-105">Additionally, the <xref:System.Media.SoundPlayer> class enables you to load or play sounds asynchronously.</span></span>  
  
 <span data-ttu-id="eadbb-106">También puede utilizar la clase <xref:System.Media.SystemSounds> para reproducir sonidos de sistema comunes, incluso un bip. </span><span class="sxs-lookup"><span data-stu-id="eadbb-106">You can also use the <xref:System.Media.SystemSounds> class to play common system sounds, including a beep.</span></span>  
  
## <a name="commonly-used-properties-methods-and-events"></a><span data-ttu-id="eadbb-107">Propiedades, métodos y eventos de uso común</span><span class="sxs-lookup"><span data-stu-id="eadbb-107">Commonly Used Properties, Methods, and Events</span></span>  
  
|<span data-ttu-id="eadbb-108">Name</span><span class="sxs-lookup"><span data-stu-id="eadbb-108">Name</span></span>|<span data-ttu-id="eadbb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="eadbb-109">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Media.SoundPlayer.SoundLocation%2A> <span data-ttu-id="eadbb-110">propiedad</span><span class="sxs-lookup"><span data-stu-id="eadbb-110">property</span></span>|<span data-ttu-id="eadbb-111">Ruta de acceso del archivo o dirección web del sonido.</span><span class="sxs-lookup"><span data-stu-id="eadbb-111">The file path or Web address of the sound.</span></span> <span data-ttu-id="eadbb-112">Los valores admitidos pueden ser UNC o HTTP.</span><span class="sxs-lookup"><span data-stu-id="eadbb-112">Acceptable values can be UNC or HTTP.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadTimeout%2A> <span data-ttu-id="eadbb-113">propiedad</span><span class="sxs-lookup"><span data-stu-id="eadbb-113">property</span></span>|<span data-ttu-id="eadbb-114">Número de milisegundos que el programa esperará para cargar un sonido antes de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="eadbb-114">The number of milliseconds your program will wait to load a sound before it throws an exception.</span></span> <span data-ttu-id="eadbb-115">El valor predeterminado es 10 segundos.</span><span class="sxs-lookup"><span data-stu-id="eadbb-115">The default is 10 seconds.</span></span>|  
|<xref:System.Media.SoundPlayer.IsLoadCompleted%2A> <span data-ttu-id="eadbb-116">propiedad</span><span class="sxs-lookup"><span data-stu-id="eadbb-116">property</span></span>|<span data-ttu-id="eadbb-117">Valor booleano que indica si el sonido finalizó la carga.</span><span class="sxs-lookup"><span data-stu-id="eadbb-117">A Boolean value indicating whether the sound has finished loading.</span></span>|  
|<xref:System.Media.SoundPlayer.Load%2A> <span data-ttu-id="eadbb-118">método</span><span class="sxs-lookup"><span data-stu-id="eadbb-118">method</span></span>|<span data-ttu-id="eadbb-119">Carga un sonido de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="eadbb-119">Loads a sound synchronously.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadAsync%2A> <span data-ttu-id="eadbb-120">método</span><span class="sxs-lookup"><span data-stu-id="eadbb-120">method</span></span>|<span data-ttu-id="eadbb-121">Comienza a cargar un sonido de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="eadbb-121">Begins to load a sound asynchronously.</span></span> <span data-ttu-id="eadbb-122">Una vez completada la carga, genera el <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> eventos.</span><span class="sxs-lookup"><span data-stu-id="eadbb-122">When loading is complete, it raises the <xref:System.Media.SoundPlayer.OnLoadCompleted%2A> event.</span></span>|  
|<xref:System.Media.SoundPlayer.Play%2A> <span data-ttu-id="eadbb-123">método</span><span class="sxs-lookup"><span data-stu-id="eadbb-123">method</span></span>|<span data-ttu-id="eadbb-124">Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en un nuevo subproceso.</span><span class="sxs-lookup"><span data-stu-id="eadbb-124">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in a new thread.</span></span>|  
|<xref:System.Media.SoundPlayer.PlaySync%2A> <span data-ttu-id="eadbb-125">método</span><span class="sxs-lookup"><span data-stu-id="eadbb-125">method</span></span>|<span data-ttu-id="eadbb-126">Reproduce el sonido especificado en el <xref:System.Media.SoundPlayer.SoundLocation%2A> o <xref:System.Media.SoundPlayer.Stream%2A> propiedad en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="eadbb-126">Plays the sound specified in the <xref:System.Media.SoundPlayer.SoundLocation%2A> or <xref:System.Media.SoundPlayer.Stream%2A> property in the current thread.</span></span>|  
|<xref:System.Media.SoundPlayer.Stop%2A> <span data-ttu-id="eadbb-127">método</span><span class="sxs-lookup"><span data-stu-id="eadbb-127">method</span></span>|<span data-ttu-id="eadbb-128">Detiene cualquier sonido que se esté reproduciendo.</span><span class="sxs-lookup"><span data-stu-id="eadbb-128">Stops any sound currently playing.</span></span>|  
|<xref:System.Media.SoundPlayer.LoadCompleted> <span data-ttu-id="eadbb-129">evento</span><span class="sxs-lookup"><span data-stu-id="eadbb-129">event</span></span>|<span data-ttu-id="eadbb-130">Se genera después de que se intente cargar un sonido.</span><span class="sxs-lookup"><span data-stu-id="eadbb-130">Raised after the load of a sound is attempted.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eadbb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="eadbb-131">See also</span></span>

- <xref:System.Media.SoundPlayer>
- <xref:System.Media.SystemSounds>
