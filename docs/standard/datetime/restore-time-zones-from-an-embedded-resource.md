---
description: 'Más información acerca de cómo: restaurar zonas horarias desde un recurso incrustado'
title: Procedimiento para restaurar zonas horarias de un recurso incrustado
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: 593fb392c073ca0a3b557b7d82d430b024b3d13a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702488"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="4d052-103">Procedimiento para restaurar zonas horarias de un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="4d052-103">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="4d052-104">En este tema se describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4d052-104">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="4d052-105">Para obtener información e instrucciones sobre cómo guardar zonas horarias, consulte [Cómo: guardar zonas horarias en un recurso incrustado](save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="4d052-105">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="4d052-106">Para deserializar un objeto TimeZoneInfo desde un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="4d052-106">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="4d052-107">Si la zona horaria que se va a recuperar no es una zona horaria personalizada, intente crear una instancia de ella mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4d052-107">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="4d052-108">Cree una instancia <xref:System.Resources.ResourceManager> de un objeto pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4d052-108">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="4d052-109">Si no puede determinar el nombre completo del archivo de recursos incrustado, use el [Ildasm.exe (desensamblador de IL)](../../framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d052-109">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="4d052-110">Una `.mresource` entrada identifica el recurso.</span><span class="sxs-lookup"><span data-stu-id="4d052-110">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="4d052-111">En el ejemplo, el nombre completo del recurso es `SerializeTimeZoneData.SerializedTimeZones` .</span><span class="sxs-lookup"><span data-stu-id="4d052-111">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="4d052-112">Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de zona horaria, puede recuperar una referencia a él llamando al `static` `Shared` método (en Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .</span><span class="sxs-lookup"><span data-stu-id="4d052-112">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="4d052-113">Si se produce un error en la llamada al <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método o si se va a crear una instancia de una zona horaria personalizada, recupere una cadena que contenga la zona horaria serializada llamando al <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="4d052-113">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="4d052-114">Deserializa los datos de la zona horaria llamando al <xref:System.TimeZoneInfo.FromSerializedString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4d052-114">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="4d052-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d052-115">Example</span></span>

<span data-ttu-id="4d052-116">En el siguiente ejemplo se deserializa un <xref:System.TimeZoneInfo> objeto almacenado en un archivo de recursos de .net XML incrustado.</span><span class="sxs-lookup"><span data-stu-id="4d052-116">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="4d052-117">Este código muestra el control de excepciones para asegurarse de que <xref:System.TimeZoneInfo> existe un objeto requerido por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d052-117">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="4d052-118">Primero se intenta crear una instancia <xref:System.TimeZoneInfo> de un objeto mediante la recuperación del registro mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4d052-118">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="4d052-119">Si no se puede crear una instancia de la zona horaria, el código la recupera del archivo de recursos incrustado.</span><span class="sxs-lookup"><span data-stu-id="4d052-119">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="4d052-120">Dado que los datos de las zonas horarias personalizadas (zonas horarias a las que se ha creado una instancia mediante el <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método) no se almacenan en el registro, el código no llama <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> a para crear una instancia de la zona horaria de Palmer, Antártida.</span><span class="sxs-lookup"><span data-stu-id="4d052-120">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="4d052-121">En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes de llamar al <xref:System.TimeZoneInfo.FromSerializedString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="4d052-121">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="4d052-122">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="4d052-122">Compiling the code</span></span>

<span data-ttu-id="4d052-123">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="4d052-123">This example requires:</span></span>

- <span data-ttu-id="4d052-124">Que se va a agregar al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="4d052-124">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="4d052-125">Que se importen los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="4d052-125">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="4d052-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d052-126">See also</span></span>

- [<span data-ttu-id="4d052-127">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="4d052-127">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="4d052-128">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="4d052-128">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="4d052-129">Cómo: guardar zonas horarias en un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="4d052-129">How to: Save time zones to an embedded resource</span></span>](save-time-zones-to-an-embedded-resource.md)
