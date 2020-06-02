---
title: Procedimiento para guardar zonas horarias en un recurso incrustado
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
ms.openlocfilehash: c8084cb8edff64b9d598f4fd0a62a362491c7aa7
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281250"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="e3888-102">Procedimiento para guardar zonas horarias en un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="e3888-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="e3888-103">Una aplicación que tiene en cuenta la zona horaria suele requerir la presencia de una zona horaria determinada.</span><span class="sxs-lookup"><span data-stu-id="e3888-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="e3888-104">Sin embargo, dado que la disponibilidad de <xref:System.TimeZoneInfo> objetos individuales depende de la información almacenada en el registro del sistema local, es posible que las zonas horarias disponibles normalmente no estén presentes.</span><span class="sxs-lookup"><span data-stu-id="e3888-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="e3888-105">Además, la información sobre las zonas horarias personalizadas de las que se ha creado una instancia mediante el <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método no se almacena con otra información de zona horaria en el registro.</span><span class="sxs-lookup"><span data-stu-id="e3888-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="e3888-106">Para asegurarse de que estas zonas horarias estén disponibles cuando se necesiten, puede guardarlas mediante su serialización y, posteriormente, restaurarlas mediante su deserialización.</span><span class="sxs-lookup"><span data-stu-id="e3888-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="e3888-107">Normalmente, la serialización de un <xref:System.TimeZoneInfo> objeto se produce aparte de la aplicación que tiene en cuenta la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e3888-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="e3888-108">Dependiendo del almacén de datos utilizado para contener objetos serializados <xref:System.TimeZoneInfo> , los datos de zona horaria se pueden serializar como parte de una rutina de instalación o instalación (por ejemplo, cuando los datos se almacenan en una clave de aplicación del registro) o como parte de una rutina de utilidad que se ejecuta antes de que se compile la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos XML de .net).</span><span class="sxs-lookup"><span data-stu-id="e3888-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="e3888-109">Además de un archivo de recursos que se compila con la aplicación, se pueden usar otros almacenes de datos para la información de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e3888-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="e3888-110">Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3888-110">These include the following:</span></span>

- <span data-ttu-id="e3888-111">El registro.</span><span class="sxs-lookup"><span data-stu-id="e3888-111">The registry.</span></span> <span data-ttu-id="e3888-112">Tenga en cuenta que una aplicación debe usar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizados en lugar de usar las subclaves de HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span><span class="sxs-lookup"><span data-stu-id="e3888-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="e3888-113">Archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="e3888-113">Configuration files.</span></span>

- <span data-ttu-id="e3888-114">Otros archivos del sistema.</span><span class="sxs-lookup"><span data-stu-id="e3888-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="e3888-115">Para guardar una zona horaria mediante su serialización en un archivo. resx</span><span class="sxs-lookup"><span data-stu-id="e3888-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="e3888-116">Recuperar una zona horaria existente o crear una nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e3888-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="e3888-117">Para recuperar una zona horaria existente, consulte [Cómo: obtener acceso a los objetos de zona horaria local y UTC predefinidos](access-utc-and-local.md) y [Cómo: crear instancias de un objeto TimeZoneInfo](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="e3888-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="e3888-118">Para crear una nueva zona horaria, llame a una de las sobrecargas del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e3888-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="e3888-119">Para obtener más información, consulte [Cómo: crear zonas horarias sin reglas de ajuste](create-time-zones-without-adjustment-rules.md) y [Cómo: crear zonas horarias con reglas de ajuste](create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="e3888-119">For more information, see [How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="e3888-120">Llame al <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contenga los datos de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="e3888-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="e3888-121">Cree una instancia <xref:System.IO.StreamWriter> de un objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo. resx al <xref:System.IO.StreamWriter> constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="e3888-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="e3888-122">Cree una instancia de un <xref:System.Resources.ResXResourceWriter> objeto pasando el <xref:System.IO.StreamWriter> objeto al <xref:System.Resources.ResXResourceWriter> constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="e3888-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="e3888-123">Pase la cadena serializada de la zona horaria al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="e3888-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="e3888-124">Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3888-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="e3888-125">Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e3888-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="e3888-126">Cierre el <xref:System.IO.StreamWriter> objeto llamando a su <xref:System.IO.StreamWriter.Close%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e3888-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="e3888-127">Agregue el archivo. resx generado al proyecto de Visual Studio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e3888-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="e3888-128">Con la ventana **propiedades** de Visual Studio, asegúrese de que la propiedad **acción de compilación** del archivo. resx esté establecida en **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="e3888-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="e3888-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3888-129">Example</span></span>

<span data-ttu-id="e3888-130">En el siguiente ejemplo, se serializa un <xref:System.TimeZoneInfo> objeto que representa la hora estándar central y un <xref:System.TimeZoneInfo> objeto que representa el tiempo de la estación Palmer, en un archivo de recursos XML de .net denominado SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="e3888-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="e3888-131">Normalmente, la hora estándar central se define en el registro; La estación de Palmer, la Antártida es una zona horaria personalizada.</span><span class="sxs-lookup"><span data-stu-id="e3888-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="e3888-132">En este ejemplo se serializan <xref:System.TimeZoneInfo> objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="e3888-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="e3888-133">Dado que el <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> método agrega información de encabezado completa a un archivo de recursos de .net XML, no se puede usar para agregar recursos a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="e3888-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="e3888-134">Para controlar esto, el ejemplo se comprueba para el archivo SerializedTimeZones. resx y, si existe, se almacenan todos sus recursos distintos de las dos zonas horarias serializadas en un <xref:System.Collections.Generic.Dictionary%602> objeto genérico.</span><span class="sxs-lookup"><span data-stu-id="e3888-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="e3888-135">A continuación, se elimina el archivo existente y se agregan los recursos existentes a un nuevo archivo SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="e3888-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="e3888-136">Los datos de zona horaria serializados también se agregan a este archivo.</span><span class="sxs-lookup"><span data-stu-id="e3888-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="e3888-137">Los campos de clave (o **nombre**) de los recursos no deben contener espacios incrustados.</span><span class="sxs-lookup"><span data-stu-id="e3888-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="e3888-138"><xref:System.String.Replace%28System.String%2CSystem.String%29>Se llama al método para quitar todos los espacios incrustados de los identificadores de zona horaria antes de que se asignen al archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="e3888-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="e3888-139">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="e3888-139">Compiling the code</span></span>

<span data-ttu-id="e3888-140">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e3888-140">This example requires:</span></span>

- <span data-ttu-id="e3888-141">Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.</span><span class="sxs-lookup"><span data-stu-id="e3888-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="e3888-142">Que se importen los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="e3888-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="e3888-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3888-143">See also</span></span>

- [<span data-ttu-id="e3888-144">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="e3888-144">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="e3888-145">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="e3888-145">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="e3888-146">Procedimiento para restaurar zonas horarias de un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="e3888-146">How to: Restore time zones from an embedded resource</span></span>](restore-time-zones-from-an-embedded-resource.md)
