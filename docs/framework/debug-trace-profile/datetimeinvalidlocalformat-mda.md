---
title: MDA de dateTimeInvalidLocalFormat
ms.date: 03/30/2017
helpviewer_keywords:
- dates [.NET Framework], formatting
- invalid date time local format
- invalid local formats
- MDAs (managed debugging assistants), invalid local formats
- managed debugging assistants (MDAs), invalid local formats
- dateTimeInvalidLocalFormat MDA
- date formatting
- time formatting
- UTC formatting
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
ms.openlocfilehash: b01f030c474e426cb87fb907f99f241eeb76a7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174763"
---
# <a name="datetimeinvalidlocalformat-mda"></a><span data-ttu-id="81ea3-102">MDA de dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="81ea3-102">dateTimeInvalidLocalFormat MDA</span></span>
<span data-ttu-id="81ea3-103">El MDA `dateTimeInvalidLocalFormat` se activa cuando una instancia de <xref:System.DateTime> que está almacenada como horario universal coordinado (UTC) tiene un formato pensado para usarse solo para instancias locales de <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="81ea3-103">The `dateTimeInvalidLocalFormat` MDA is activated when a <xref:System.DateTime> instance that is stored as a Universal Coordinated Time (UTC) is formatted using a format that is intended to be used only for local <xref:System.DateTime> instances.</span></span> <span data-ttu-id="81ea3-104">Este MDA no está activado para instancias de <xref:System.DateTime> sin especificar o predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="81ea3-104">This MDA is not activated for unspecified or default <xref:System.DateTime> instances.</span></span>  
  
## <a name="symptom"></a><span data-ttu-id="81ea3-105">Síntoma</span><span class="sxs-lookup"><span data-stu-id="81ea3-105">Symptom</span></span>  
 <span data-ttu-id="81ea3-106">Una aplicación está serializando manualmente una instancia de <xref:System.DateTime> UTC mediante un formato local:</span><span class="sxs-lookup"><span data-stu-id="81ea3-106">An application is manually serializing a UTC <xref:System.DateTime> instance using a local format:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### <a name="cause"></a><span data-ttu-id="81ea3-107">Causa</span><span class="sxs-lookup"><span data-stu-id="81ea3-107">Cause</span></span>  
 <span data-ttu-id="81ea3-108">El formato "z" para el método <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> incluye el desplazamiento de zona horaria local, por ejemplo, "+ 10:00" para la hora de Sydney.</span><span class="sxs-lookup"><span data-stu-id="81ea3-108">The 'z' format for the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> method includes the local time zone offset, for example, "+10:00" for Sydney time.</span></span> <span data-ttu-id="81ea3-109">Por lo tanto, solo genera un resultado significativo si el valor de <xref:System.DateTime> es local.</span><span class="sxs-lookup"><span data-stu-id="81ea3-109">As such, it will only produce a meaningful result if the value of the <xref:System.DateTime> is local.</span></span> <span data-ttu-id="81ea3-110">Si el valor es la hora UTC, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> incluye el desplazamiento de zona horaria local, pero no muestra ni ajusta el especificador de zona horaria.</span><span class="sxs-lookup"><span data-stu-id="81ea3-110">If the value is UTC time, <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> includes the local time zone offset, but it does not display or adjust the time zone specifier.</span></span>  
  
### <a name="resolution"></a><span data-ttu-id="81ea3-111">Solución</span><span class="sxs-lookup"><span data-stu-id="81ea3-111">Resolution</span></span>  
 <span data-ttu-id="81ea3-112">Las instancias de <xref:System.DateTime> UTC deben tener el formato de una manera que indique que son UTC.</span><span class="sxs-lookup"><span data-stu-id="81ea3-112">UTC <xref:System.DateTime> instances should be formatted in a way that indicates that they are UTC.</span></span> <span data-ttu-id="81ea3-113">El formato recomendado para la hora UTC es usar un carácter "Z" para indicar la hora UTC:</span><span class="sxs-lookup"><span data-stu-id="81ea3-113">The recommended format for UTC times to use a 'Z' to denote UTC time:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 <span data-ttu-id="81ea3-114">También hay un formato "o" que serializa un instancia de <xref:System.DateTime> mediante la propiedad <xref:System.DateTime.Kind%2A>, que serializa correctamente independientemente de si la instancia es local, UTC o sin especificar:</span><span class="sxs-lookup"><span data-stu-id="81ea3-114">There is also an "o" format that serializes a <xref:System.DateTime> making use of the <xref:System.DateTime.Kind%2A> property that serializes correctly regardless of whether the instance is local, UTC, or unspecified:</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="81ea3-115">Efecto en el Runtime</span><span class="sxs-lookup"><span data-stu-id="81ea3-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="81ea3-116">Este MDA no afecta al tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="81ea3-116">This MDA does not affect the runtime.</span></span>  
  
## <a name="output"></a><span data-ttu-id="81ea3-117">Output</span><span class="sxs-lookup"><span data-stu-id="81ea3-117">Output</span></span>  
 <span data-ttu-id="81ea3-118">No hay ningún resultado especial como consecuencia de la activación de este MDA, aunque se puede usar la pila de llamadas para determinar la ubicación de la llamada a <xref:System.DateTime.ToString%2A> que ha activado el MDA.</span><span class="sxs-lookup"><span data-stu-id="81ea3-118">There is no special output as a result of this MDA activating., However, the call stack can be used to determine the location of the <xref:System.DateTime.ToString%2A> call that activated the MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="81ea3-119">Configuración</span><span class="sxs-lookup"><span data-stu-id="81ea3-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="81ea3-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81ea3-120">Example</span></span>  
 <span data-ttu-id="81ea3-121">Imagine una aplicación que está serializando indirectamente un valor <xref:System.DateTime> UTC mediante la clase <xref:System.Xml.XmlConvert> o <xref:System.Data.DataSet> de la siguiente manera.</span><span class="sxs-lookup"><span data-stu-id="81ea3-121">Consider an application that is indirectly serializing a UTC <xref:System.DateTime> value by using the <xref:System.Xml.XmlConvert> or <xref:System.Data.DataSet> class, in the following manner.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <span data-ttu-id="81ea3-122">Las serializaciones <xref:System.Xml.XmlConvert> y <xref:System.Data.DataSet> usan formatos locales para la serialización de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="81ea3-122">The <xref:System.Xml.XmlConvert> and <xref:System.Data.DataSet> serializations use local formats for serialization by default.</span></span> <span data-ttu-id="81ea3-123">Se necesitan opciones adicionales para serializar otros tipos de valores <xref:System.DateTime>, como UTC.</span><span class="sxs-lookup"><span data-stu-id="81ea3-123">Additional options are required to serialize other kinds of <xref:System.DateTime> values, such as UTC.</span></span>  
  
 <span data-ttu-id="81ea3-124">Para obtener este ejemplo concreto, pase `XmlDateTimeSerializationMode.RoundtripKind` a la llamada a `ToString` en `XmlConvert`.</span><span class="sxs-lookup"><span data-stu-id="81ea3-124">For this specific example, pass in `XmlDateTimeSerializationMode.RoundtripKind` to the `ToString` call on `XmlConvert`.</span></span> <span data-ttu-id="81ea3-125">Con esto se serializan los datos como una hora UTC.</span><span class="sxs-lookup"><span data-stu-id="81ea3-125">This serializes the data as a UTC time.</span></span>  
  
 <span data-ttu-id="81ea3-126">Si usa <xref:System.Data.DataSet>, establezca la propiedad <xref:System.Data.DataColumn.DateTimeMode%2A> del objeto <xref:System.Data.DataColumn> en <xref:System.Data.DataSetDateTime.Utc>.</span><span class="sxs-lookup"><span data-stu-id="81ea3-126">If using a <xref:System.Data.DataSet>, set the <xref:System.Data.DataColumn.DateTimeMode%2A> property on the <xref:System.Data.DataColumn> object to <xref:System.Data.DataSetDateTime.Utc>.</span></span>  
  
```csharp
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## <a name="see-also"></a><span data-ttu-id="81ea3-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="81ea3-127">See also</span></span>

- <xref:System.Globalization.DateTimeFormatInfo>
- [<span data-ttu-id="81ea3-128">Diagnóstico de errores con asistentes para la depuración administrada</span><span class="sxs-lookup"><span data-stu-id="81ea3-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
