---
title: 'Cómo: guardar zonas horarias en un recurso incrustado'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 921874e774d18751c29db495dac1bc53d10cc8ad
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44211858"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="b32ee-102">Cómo: guardar zonas horarias en un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="b32ee-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="b32ee-103">Una aplicación compatible con zona horaria a menudo requiere la presencia de una zona horaria determinada.</span><span class="sxs-lookup"><span data-stu-id="b32ee-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="b32ee-104">Sin embargo, dado que la disponibilidad de la persona <xref:System.TimeZoneInfo> objetos depende de la información almacenada en el registro del sistema local, las zonas horarias disponibles habitualmente incluso puede que falte.</span><span class="sxs-lookup"><span data-stu-id="b32ee-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="b32ee-105">Además, crea una instancia de información sobre zonas horarias personalizadas mediante el uso de la <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se almacena con otra información de zona horaria en el registro.</span><span class="sxs-lookup"><span data-stu-id="b32ee-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="b32ee-106">Para asegurarse de que estas zonas horarias están disponibles cuando se necesiten, puede serializarlas para ellos y restaurarlas más adelante mediante la deserialización de ellos.</span><span class="sxs-lookup"><span data-stu-id="b32ee-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="b32ee-107">Normalmente, serializar un <xref:System.TimeZoneInfo> objeto aparece además de las aplicaciones basadas en la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b32ee-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="b32ee-108">Según el almacén de datos que se usa para contener serializada <xref:System.TimeZoneInfo> objetos, datos de zona horaria se pueden serializar como parte de una rutina de configuración o instalación (por ejemplo, cuando los datos se almacenan en una clave del registro de aplicación), o como parte de una rutina de la utilidad que se ejecuta antes de que se compila la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (.resx) XML. NET).</span><span class="sxs-lookup"><span data-stu-id="b32ee-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="b32ee-109">Un archivo de recursos que se compila con la aplicación, además de otros almacenes de datos pueden utilizarse para obtener información de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b32ee-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="b32ee-110">Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b32ee-110">These include the following:</span></span>

* <span data-ttu-id="b32ee-111">El registro.</span><span class="sxs-lookup"><span data-stu-id="b32ee-111">The registry.</span></span> <span data-ttu-id="b32ee-112">Tenga en cuenta que una aplicación debe utilizar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizada en lugar de utilizar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span><span class="sxs-lookup"><span data-stu-id="b32ee-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="b32ee-113">Archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="b32ee-113">Configuration files.</span></span>

* <span data-ttu-id="b32ee-114">Otros archivos del sistema.</span><span class="sxs-lookup"><span data-stu-id="b32ee-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="b32ee-115">Para guardar una zona horaria serializándolo en un archivo .resx</span><span class="sxs-lookup"><span data-stu-id="b32ee-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="b32ee-116">Recuperar una zona horaria existente o crear una nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b32ee-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="b32ee-117">Para recuperar una zona horaria existente, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](../../../docs/standard/datetime/access-utc-and-local.md) y [Cómo: crear una instancia de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="b32ee-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="b32ee-118">Para crear una nueva zona horaria, llame a una de las sobrecargas de los <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b32ee-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="b32ee-119">Para obtener más información, consulte [Cómo: crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b32ee-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="b32ee-120">Llame a la <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contiene los datos de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="b32ee-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="b32ee-121">Crear una instancia de un <xref:System.IO.StreamWriter> objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo .resx que el <xref:System.IO.StreamWriter> constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="b32ee-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="b32ee-122">Crear una instancia de un <xref:System.Resources.ResXResourceWriter> pasando el <xref:System.IO.StreamWriter> de objeto para el <xref:System.Resources.ResXResourceWriter> constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="b32ee-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="b32ee-123">Pase la zona horaria serializa la cadena para el <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="b32ee-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="b32ee-124">Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b32ee-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="b32ee-125">Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b32ee-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="b32ee-126">Cerrar la <xref:System.IO.StreamWriter> objeto mediante una llamada a su <xref:System.IO.StreamWriter.Close%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b32ee-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="b32ee-127">Agregue el archivo .resx generado al proyecto de Visual Studio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b32ee-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="b32ee-128">Mediante el **propiedades** ventana en Visual Studio, asegúrese de que el archivo .resx **acción de compilación** propiedad está establecida en **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="b32ee-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="b32ee-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b32ee-129">Example</span></span>

<span data-ttu-id="b32ee-130">El ejemplo siguiente se serializa un <xref:System.TimeZoneInfo> objeto que representa la hora estándar Central y un <xref:System.TimeZoneInfo> objeto que representa la Estación Palmer, la hora de Antártida en un archivo de recursos XML de .NET que se denomina SerializedTimeZones.resx.</span><span class="sxs-lookup"><span data-stu-id="b32ee-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="b32ee-131">Hora estándar central normalmente se define en el registro; Estación Palmer, Antártida es una zona horaria personalizada.</span><span class="sxs-lookup"><span data-stu-id="b32ee-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="b32ee-132">En este ejemplo, se serializa <xref:System.TimeZoneInfo> objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="b32ee-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="b32ee-133">Dado que el <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> método agrega información de encabezado completa a un archivo de recursos XML de .NET, no se puede usar para agregar recursos a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="b32ee-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="b32ee-134">El ejemplo controla mediante la comprobación del archivo SerializedTimeZones.resx y, si existe, almacenar todos sus recursos distintos de las dos zonas horarias serializan en un tipo genérico <xref:System.Collections.Generic.Dictionary%602> objeto.</span><span class="sxs-lookup"><span data-stu-id="b32ee-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="b32ee-135">A continuación, se elimina el archivo existente y los recursos existentes se agregan a un nuevo archivo SerializedTimeZones.resx.</span><span class="sxs-lookup"><span data-stu-id="b32ee-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="b32ee-136">Los datos de zona horaria serializada también se agregan a este archivo.</span><span class="sxs-lookup"><span data-stu-id="b32ee-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="b32ee-137">La clave (o **nombre**) los campos de recursos no deben contener espacios incrustados.</span><span class="sxs-lookup"><span data-stu-id="b32ee-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="b32ee-138">El <xref:System.String.Replace%28System.String%2CSystem.String%29> método se llama para quitar todos los espacios insertados en los identificadores de zona horaria antes de que están asignadas al archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="b32ee-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b32ee-139">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="b32ee-139">Compiling the code</span></span>

<span data-ttu-id="b32ee-140">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b32ee-140">This example requires:</span></span>

* <span data-ttu-id="b32ee-141">Que se agregarán al proyecto una referencia a System.Windows.Forms.dll y System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="b32ee-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="b32ee-142">Que se importarán los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="b32ee-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="b32ee-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b32ee-143">See also</span></span>

* [<span data-ttu-id="b32ee-144">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="b32ee-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
* [<span data-ttu-id="b32ee-145">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="b32ee-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
* [<span data-ttu-id="b32ee-146">Restauración de zonas horarias de un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="b32ee-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
