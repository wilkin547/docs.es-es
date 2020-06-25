---
title: 'Mensajes de protobuf: gRPC para desarrolladores de WCF'
description: Obtenga información sobre cómo se definen los mensajes de protobuf en el IDL y se generan en C#.
ms.date: 09/09/2019
ms.openlocfilehash: 6fc7b9c34810abaa8d674af56d1517a5cf87521b
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325041"
---
# <a name="protobuf-messages"></a><span data-ttu-id="e8ca6-103">Mensajes de Protobuf</span><span class="sxs-lookup"><span data-stu-id="e8ca6-103">Protobuf messages</span></span>

<span data-ttu-id="e8ca6-104">En esta sección se explica cómo declarar mensajes de búfer de protocolo (protobuf) en `.proto` archivos.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="e8ca6-105">En él se explican los conceptos fundamentales de los números y tipos de campo, y se examina el código de C# generado por el `protoc` compilador.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="e8ca6-106">En el resto del capítulo veremos con más detalle cómo se representan los distintos tipos de datos en protobuf.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="e8ca6-107">Declarar un mensaje</span><span class="sxs-lookup"><span data-stu-id="e8ca6-107">Declaring a message</span></span>

<span data-ttu-id="e8ca6-108">En Windows Communication Foundation (WCF), una `Stock` clase para una aplicación bursátil de stock market podría definirse como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8ca6-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

```csharp
namespace TraderSys
{
    [DataContract]
    public class Stock
    {
        [DataMember]
        public int Id { get; set;}
        [DataMember]
        public string Symbol { get; set;}
        [DataMember]
        public string DisplayName { get; set;}
        [DataMember]
        public int MarketId { get; set; }
    }
}
```

<span data-ttu-id="e8ca6-109">Para implementar la clase equivalente en protobuf, debe declararla en el `.proto` archivo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="e8ca6-110">`protoc`Después, el compilador generará la clase .net como parte del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="e8ca6-111">La primera línea declara la versión de sintaxis que se está usando.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="e8ca6-112">La versión 3 del idioma se lanzó en 2016.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="e8ca6-113">Es la versión que recomendamos para gRPC Services.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="e8ca6-114">La `option csharp_namespace` línea especifica el espacio de nombres que se va a usar para los tipos de C# generados.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="e8ca6-115">Esta opción se omitirá cuando el `.proto` archivo se compile para otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="e8ca6-116">Los archivos protobuf a menudo contienen opciones específicas del idioma para varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="e8ca6-117">La `Stock` definición del mensaje especifica cuatro campos.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="e8ca6-118">Cada tiene un tipo, un nombre y un número de campo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="e8ca6-119">Números de campo</span><span class="sxs-lookup"><span data-stu-id="e8ca6-119">Field numbers</span></span>

<span data-ttu-id="e8ca6-120">Los números de campo son una parte importante de protobuf.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="e8ca6-121">Se usan para identificar los campos en los datos codificados binarios, lo que significa que no pueden cambiar de una versión a la versión del servicio.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="e8ca6-122">La ventaja es que es posible la compatibilidad con versiones anteriores y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="e8ca6-123">Los clientes y servicios simplemente omitirán los números de campo que no conozcan, siempre y cuando se controle la posibilidad de que se produzcan valores.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="e8ca6-124">En el formato binario, el número de campo se combina con un identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="e8ca6-125">Los números de campo de 1 a 15 se pueden codificar con su tipo como un solo byte.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="e8ca6-126">Los números de 16 a 2.047 toman 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="e8ca6-127">Puede continuar si necesita más de 2.047 campos en un mensaje por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="e8ca6-128">Los identificadores de un solo byte para los números de campo 1 a 15 ofrecen un mejor rendimiento, por lo que debe usarlos para los campos más básicos que se usan con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="e8ca6-129">Tipos</span><span class="sxs-lookup"><span data-stu-id="e8ca6-129">Types</span></span>

<span data-ttu-id="e8ca6-130">Las declaraciones de tipos usan los tipos de datos escalares nativos de protobuf, que se describen con más detalle en [la sección siguiente](protobuf-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="e8ca6-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="e8ca6-131">En el resto de este capítulo se tratarán los tipos integrados de protobuf y se mostrará cómo se relacionan con los tipos comunes de .NET.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="e8ca6-132">Protobuf no admite de forma nativa un `decimal` tipo, por lo que `double` se usa en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="e8ca6-133">En el caso de las aplicaciones que requieren una precisión decimal completa, consulte la [sección decimales](protobuf-data-types.md#decimals) en la siguiente parte de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="e8ca6-134">El código generado</span><span class="sxs-lookup"><span data-stu-id="e8ca6-134">The generated code</span></span>

<span data-ttu-id="e8ca6-135">Al compilar la aplicación, protobuf crea clases para cada uno de los mensajes, asignando sus tipos nativos a tipos de C#.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="e8ca6-136">El `Stock` tipo generado tendría la firma siguiente:</span><span class="sxs-lookup"><span data-stu-id="e8ca6-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="e8ca6-137">El código real que se genera es mucho más complicado que este.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="e8ca6-138">La razón es que cada clase contiene todo el código necesario para serializar y deserializar en el formato de conexión binaria.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="e8ca6-139">Nombres de propiedad</span><span class="sxs-lookup"><span data-stu-id="e8ca6-139">Property names</span></span>

<span data-ttu-id="e8ca6-140">Tenga en cuenta que el compilador protobuf `PascalCase` se aplica a los nombres de propiedad, aunque se encontraban `snake_case` en el `.proto` archivo.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="e8ca6-141">La [Guía de estilo de protobuf](https://developers.google.com/protocol-buffers/docs/style) recomienda el uso `snake_case` de en las definiciones de mensaje para que la generación de código para otras plataformas produzca el caso esperado de sus convenciones.</span><span class="sxs-lookup"><span data-stu-id="e8ca6-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e8ca6-142">[Anterior](protocol-buffers.md)
>[Siguiente](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="e8ca6-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
