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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ca39d989cc7bc16ec2678ba5fa53710899f3ac4
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107153"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="36f96-102">Procedimiento para guardar zonas horarias en un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="36f96-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="36f96-103">Una aplicación que tiene en cuenta la zona horaria suele requerir la presencia de una zona horaria determinada.</span><span class="sxs-lookup"><span data-stu-id="36f96-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="36f96-104">Sin embargo, dado que la disponibilidad <xref:System.TimeZoneInfo> de objetos individuales depende de la información almacenada en el registro del sistema local, es posible que las zonas horarias disponibles normalmente no estén presentes.</span><span class="sxs-lookup"><span data-stu-id="36f96-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="36f96-105">Además, la información sobre las zonas horarias personalizadas de las que <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> se ha creado una instancia mediante el método no se almacena con otra información de zona horaria en el registro.</span><span class="sxs-lookup"><span data-stu-id="36f96-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="36f96-106">Para asegurarse de que estas zonas horarias estén disponibles cuando se necesiten, puede guardarlas mediante su serialización y, posteriormente, restaurarlas mediante su deserialización.</span><span class="sxs-lookup"><span data-stu-id="36f96-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="36f96-107">Normalmente, la serialización <xref:System.TimeZoneInfo> de un objeto se produce aparte de la aplicación que tiene en cuenta la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="36f96-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="36f96-108">Dependiendo del almacén de datos utilizado para contener <xref:System.TimeZoneInfo> objetos serializados, los datos de zona horaria se pueden serializar como parte de una rutina de instalación o configuración (por ejemplo, cuando los datos se almacenan en una clave de aplicación del registro) o como parte de una rutina de utilidad que ejecuta antes de que se compile la aplicación final (por ejemplo, cuando los datos serializados se almacenan en un archivo de recursos (. resx) de .NET XML).</span><span class="sxs-lookup"><span data-stu-id="36f96-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="36f96-109">Además de un archivo de recursos que se compila con la aplicación, se pueden usar otros almacenes de datos para la información de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="36f96-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="36f96-110">Entre ellas se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="36f96-110">These include the following:</span></span>

- <span data-ttu-id="36f96-111">El registro.</span><span class="sxs-lookup"><span data-stu-id="36f96-111">The registry.</span></span> <span data-ttu-id="36f96-112">Tenga en cuenta que una aplicación debe usar las subclaves de su propia clave de aplicación para almacenar datos de zona horaria personalizados en lugar de usar las subclaves de HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span><span class="sxs-lookup"><span data-stu-id="36f96-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="36f96-113">Archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="36f96-113">Configuration files.</span></span>

- <span data-ttu-id="36f96-114">Otros archivos del sistema.</span><span class="sxs-lookup"><span data-stu-id="36f96-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="36f96-115">Para guardar una zona horaria mediante su serialización en un archivo. resx</span><span class="sxs-lookup"><span data-stu-id="36f96-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="36f96-116">Recuperar una zona horaria existente o crear una nueva zona horaria.</span><span class="sxs-lookup"><span data-stu-id="36f96-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="36f96-117">Para recuperar una zona horaria existente, consulte [cómo: Obtener acceso a los objetos](../../../docs/standard/datetime/access-utc-and-local.md) de zona horaria local y UTC predefinidos y [cómo: Cree una instancia de un](../../../docs/standard/datetime/instantiate-time-zone-info.md)objeto TimeZoneInfo.</span><span class="sxs-lookup"><span data-stu-id="36f96-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="36f96-118">Para crear una nueva zona horaria, llame a una de las sobrecargas del <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> método.</span><span class="sxs-lookup"><span data-stu-id="36f96-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="36f96-119">Para obtener más información, consulte [Cómo Cree zonas horarias sin reglas](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) de [ajuste y cómo: Cree zonas horarias con reglas](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)de ajuste.</span><span class="sxs-lookup"><span data-stu-id="36f96-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="36f96-120">Llame al <xref:System.TimeZoneInfo.ToSerializedString%2A> método para crear una cadena que contenga los datos de la zona horaria.</span><span class="sxs-lookup"><span data-stu-id="36f96-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="36f96-121">Cree una instancia <xref:System.IO.StreamWriter> de un objeto proporcionando el nombre y, opcionalmente, la ruta de acceso del archivo <xref:System.IO.StreamWriter> . resx al constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="36f96-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="36f96-122">Cree una instancia <xref:System.Resources.ResXResourceWriter> de un objeto pasando <xref:System.IO.StreamWriter> el objeto al <xref:System.Resources.ResXResourceWriter> constructor de clase.</span><span class="sxs-lookup"><span data-stu-id="36f96-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="36f96-123">Pase la cadena serializada de la zona horaria al <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="36f96-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="36f96-124">Llame al método <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f96-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="36f96-125">Llame al método <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36f96-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="36f96-126">Cierre el <xref:System.IO.StreamWriter> objeto llamando a su <xref:System.IO.StreamWriter.Close%2A> método.</span><span class="sxs-lookup"><span data-stu-id="36f96-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="36f96-127">Agregue el archivo. resx generado al proyecto de Visual Studio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="36f96-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="36f96-128">Con la ventana **propiedades** de Visual Studio, asegúrese de que la propiedad **acción de compilación** del archivo. resx esté establecida en **recurso incrustado**.</span><span class="sxs-lookup"><span data-stu-id="36f96-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="36f96-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="36f96-129">Example</span></span>

<span data-ttu-id="36f96-130">En el siguiente ejemplo, se <xref:System.TimeZoneInfo> serializa un objeto que representa la hora estándar <xref:System.TimeZoneInfo> central y un objeto que representa el tiempo de la estación Palmer, en un archivo de recursos XML de .net denominado SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="36f96-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="36f96-131">Normalmente, la hora estándar central se define en el registro; La estación de Palmer, la Antártida es una zona horaria personalizada.</span><span class="sxs-lookup"><span data-stu-id="36f96-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="36f96-132">En este ejemplo se <xref:System.TimeZoneInfo> serializan objetos para que estén disponibles en un archivo de recursos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="36f96-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="36f96-133">Dado que <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> el método agrega información de encabezado completa a un archivo de recursos de .net XML, no se puede usar para agregar recursos a un archivo existente.</span><span class="sxs-lookup"><span data-stu-id="36f96-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="36f96-134">Para controlar esto, el ejemplo se comprueba para el archivo SerializedTimeZones. resx y, si existe, se almacenan todos sus recursos distintos de las dos zonas horarias serializadas <xref:System.Collections.Generic.Dictionary%602> en un objeto genérico.</span><span class="sxs-lookup"><span data-stu-id="36f96-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="36f96-135">A continuación, se elimina el archivo existente y se agregan los recursos existentes a un nuevo archivo SerializedTimeZones. resx.</span><span class="sxs-lookup"><span data-stu-id="36f96-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="36f96-136">Los datos de zona horaria serializados también se agregan a este archivo.</span><span class="sxs-lookup"><span data-stu-id="36f96-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="36f96-137">Los campos de clave (o **nombre**) de los recursos no deben contener espacios incrustados.</span><span class="sxs-lookup"><span data-stu-id="36f96-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="36f96-138">Se llama al método para quitar todos los espacios incrustados de los identificadores de zona horaria antes de que se asignen al archivo de recursos. <xref:System.String.Replace%28System.String%2CSystem.String%29></span><span class="sxs-lookup"><span data-stu-id="36f96-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="36f96-139">Compilación del código</span><span class="sxs-lookup"><span data-stu-id="36f96-139">Compiling the code</span></span>

<span data-ttu-id="36f96-140">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="36f96-140">This example requires:</span></span>

- <span data-ttu-id="36f96-141">Que se va a agregar al proyecto una referencia a System. Windows. Forms. dll y System. Core. dll.</span><span class="sxs-lookup"><span data-stu-id="36f96-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="36f96-142">Que se importen los espacios de nombres siguientes:</span><span class="sxs-lookup"><span data-stu-id="36f96-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="36f96-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="36f96-143">See also</span></span>

- [<span data-ttu-id="36f96-144">Fechas, horas y zonas horarias</span><span class="sxs-lookup"><span data-stu-id="36f96-144">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="36f96-145">Información general sobre zonas horarias</span><span class="sxs-lookup"><span data-stu-id="36f96-145">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="36f96-146">Procedimientos: Restauración de zonas horarias desde un recurso incrustado</span><span class="sxs-lookup"><span data-stu-id="36f96-146">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)
