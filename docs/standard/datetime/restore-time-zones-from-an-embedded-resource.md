---
title: Procedimiento Restaurar zonas horarias de un recurso incrustado
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71fc4e04c87dfa3b83eabb06361d1da94a512a5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656810"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="32c5e-102">Procedimiento Restaurar zonas horarias de un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="32c5e-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="32c5e-103">Este tema describe cómo restaurar zonas horarias que se han guardado en un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="32c5e-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="32c5e-104">Para obtener información e instrucciones acerca de cómo guardar zonas horarias, vea [Cómo: Guardar zonas horarias en un recurso incrustado](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="32c5e-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="32c5e-105">Para deserializar un objeto TimeZoneInfo de un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="32c5e-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="32c5e-106">Si la zona horaria va a recuperar no es una zona horaria personalizada, intente crear instancias mediante la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="32c5e-107">Crear una instancia de un <xref:System.Resources.ResourceManager> pasando el nombre completo del archivo de recursos incrustado y una referencia al ensamblado que contiene el archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="32c5e-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="32c5e-108">Si no se puede determinar el nombre completo del archivo de recursos incrustado, utilice la [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="32c5e-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="32c5e-109">Un `.mresource` entrada identifica el recurso.</span><span class="sxs-lookup"><span data-stu-id="32c5e-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="32c5e-110">En el ejemplo, es el nombre completo del recurso `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="32c5e-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="32c5e-111">Si el archivo de recursos está incrustado en el mismo ensamblado que contiene el código de creación de instancias de la zona horaria, puede recuperar una referencia a él mediante una llamada a la `static` (`Shared` en Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="32c5e-112">Si la llamada a la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método se produce un error, o si es una zona horaria personalizada que se creará una instancia, recuperar una cadena que contiene la zona horaria serializada mediante una llamada a la <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="32c5e-113">Deserializar los datos de zona horaria mediante una llamada a la <xref:System.TimeZoneInfo.FromSerializedString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="32c5e-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32c5e-114">Example</span></span>

<span data-ttu-id="32c5e-115">El siguiente ejemplo se deserializa un <xref:System.TimeZoneInfo> objeto almacenado en un archivo de recursos de .NET XML incrustado.</span><span class="sxs-lookup"><span data-stu-id="32c5e-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="32c5e-116">Este código muestra el control de excepciones para asegurarse de que un <xref:System.TimeZoneInfo> objeto requerido por la aplicación está presente.</span><span class="sxs-lookup"><span data-stu-id="32c5e-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="32c5e-117">Primero intenta crear una instancia de un <xref:System.TimeZoneInfo> objeto recuperarlos desde el registro mediante el <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="32c5e-118">Si no pueden crearse instancias de la zona horaria, el código recupera del archivo de recursos incrustado.</span><span class="sxs-lookup"><span data-stu-id="32c5e-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="32c5e-119">Porque datos para las zonas horarias personalizadas (zonas horarias que crea una instancia mediante el <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método) no se almacenan en el registro, el código no llama a la <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> para crear instancias de la zona horaria para Palmer, Antártida.</span><span class="sxs-lookup"><span data-stu-id="32c5e-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="32c5e-120">En su lugar, busca inmediatamente en el archivo de recursos incrustado para recuperar una cadena que contiene los datos de la zona horaria antes de llamar a la <xref:System.TimeZoneInfo.FromSerializedString%2A> método.</span><span class="sxs-lookup"><span data-stu-id="32c5e-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="32c5e-121">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="32c5e-121">Compiling the code</span></span>

<span data-ttu-id="32c5e-122">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="32c5e-122">This example requires:</span></span>

* <span data-ttu-id="32c5e-123">Que se agregarán al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="32c5e-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="32c5e-124">Que se importarán los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="32c5e-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="32c5e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="32c5e-125">See also</span></span>

- [<span data-ttu-id="32c5e-126">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="32c5e-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="32c5e-127">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="32c5e-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="32c5e-128">Cómo: Guardar zonas horarias en un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="32c5e-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
