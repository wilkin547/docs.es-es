---
title: Mensajes de Protobuf - gRPC para desarrolladores de WCF
description: Obtenga más información sobre cómo se definen los mensajes de Protobuf en el IDL y se generan en C.
ms.date: 09/09/2019
ms.openlocfilehash: 5b3d4383de39a3785ef804fec21939a740f54669
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147989"
---
# <a name="protobuf-messages"></a><span data-ttu-id="e411f-103">Mensajes de Protobuf</span><span class="sxs-lookup"><span data-stu-id="e411f-103">Protobuf messages</span></span>

<span data-ttu-id="e411f-104">En esta sección se explica cómo declarar mensajes `.proto` de búfer de protocolo (Protobuf) en archivos.</span><span class="sxs-lookup"><span data-stu-id="e411f-104">This section covers how to declare Protocol Buffer (Protobuf) messages in `.proto` files.</span></span> <span data-ttu-id="e411f-105">En él se explican los conceptos fundamentales de los tipos `protoc` y números de campo y se examina el código de C- que genera el compilador.</span><span class="sxs-lookup"><span data-stu-id="e411f-105">It explains the fundamental concepts of field numbers and types, and it looks at the C# code that the `protoc` compiler generates.</span></span>

<span data-ttu-id="e411f-106">El resto del capítulo examinará con más detalle cómo se representan los diferentes tipos de datos en Protobuf.</span><span class="sxs-lookup"><span data-stu-id="e411f-106">The rest of the chapter will look in more detail at how different types of data are represented in Protobuf.</span></span>

## <a name="declaring-a-message"></a><span data-ttu-id="e411f-107">Declarar un mensaje</span><span class="sxs-lookup"><span data-stu-id="e411f-107">Declaring a message</span></span>

<span data-ttu-id="e411f-108">En Windows Communication Foundation `Stock` (WCF), una clase para una aplicación de trading en el mercado de valores podría definirse como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e411f-108">In Windows Communication Foundation (WCF), a `Stock` class for a stock market trading application might be defined like the following example:</span></span>

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

<span data-ttu-id="e411f-109">Para implementar la clase equivalente en Protobuf, `.proto` debe declararla en el archivo.</span><span class="sxs-lookup"><span data-stu-id="e411f-109">To implement the equivalent class in Protobuf, you must declare it in the `.proto` file.</span></span> <span data-ttu-id="e411f-110">A `protoc` continuación, el compilador generará la clase .NET como parte del proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="e411f-110">The `protoc` compiler will then generate the .NET class as part of the build process.</span></span>

```protobuf
syntax "proto3";

option csharp_namespace = "TraderSys";

message Stock {

    int32 id = 1;
    string symbol = 2;
    string display_name = 3;
    int32 market_id = 4;

}  
```

<span data-ttu-id="e411f-111">La primera línea declara la versión de sintaxis que se está utilizando.</span><span class="sxs-lookup"><span data-stu-id="e411f-111">The first line declares the syntax version being used.</span></span> <span data-ttu-id="e411f-112">La versión 3 del idioma fue lanzada en 2016.</span><span class="sxs-lookup"><span data-stu-id="e411f-112">Version 3 of the language was released in 2016.</span></span> <span data-ttu-id="e411f-113">Es la versión que recomendamos para los servicios gRPC.</span><span class="sxs-lookup"><span data-stu-id="e411f-113">It's the version that we recommend for gRPC services.</span></span>

<span data-ttu-id="e411f-114">La `option csharp_namespace` línea especifica el espacio de nombres que se usará para los tipos generados de C.</span><span class="sxs-lookup"><span data-stu-id="e411f-114">The `option csharp_namespace` line specifies the namespace to be used for the generated C# types.</span></span> <span data-ttu-id="e411f-115">Esta opción se omitirá cuando el `.proto` archivo se compile para otros idiomas.</span><span class="sxs-lookup"><span data-stu-id="e411f-115">This option will be ignored when the `.proto` file is compiled for other languages.</span></span> <span data-ttu-id="e411f-116">Los archivos Protobuf a menudo contienen opciones específicas del idioma para varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="e411f-116">Protobuf files often contain language-specific options for several languages.</span></span>

<span data-ttu-id="e411f-117">La `Stock` definición del mensaje especifica cuatro campos.</span><span class="sxs-lookup"><span data-stu-id="e411f-117">The `Stock` message definition specifies four fields.</span></span> <span data-ttu-id="e411f-118">Cada uno tiene un tipo, un nombre y un número de campo.</span><span class="sxs-lookup"><span data-stu-id="e411f-118">Each has a type, a name, and a field number.</span></span>

## <a name="field-numbers"></a><span data-ttu-id="e411f-119">Números de campo</span><span class="sxs-lookup"><span data-stu-id="e411f-119">Field numbers</span></span>

<span data-ttu-id="e411f-120">Los números de campo son una parte importante de Protobuf.</span><span class="sxs-lookup"><span data-stu-id="e411f-120">Field numbers are an important part of Protobuf.</span></span> <span data-ttu-id="e411f-121">Se usan para identificar campos en los datos codificados binarios, lo que significa que no pueden cambiar de versión a versión del servicio.</span><span class="sxs-lookup"><span data-stu-id="e411f-121">They're used to identify fields in the binary encoded data, which means they can't change from version to version of your service.</span></span> <span data-ttu-id="e411f-122">La ventaja es que la compatibilidad con versiones anteriores y la compatibilidad hacia delante son posibles.</span><span class="sxs-lookup"><span data-stu-id="e411f-122">The advantage is that backward compatibility and forward compatibility are possible.</span></span> <span data-ttu-id="e411f-123">Los clientes y servicios simplemente ignorarán los números de campo que no conocen, siempre y cuando se maneje la posibilidad de que falten valores.</span><span class="sxs-lookup"><span data-stu-id="e411f-123">Clients and services will simply ignore field numbers that they don't know about, as long as the possibility of missing values is handled.</span></span>

<span data-ttu-id="e411f-124">En el formato binario, el número de campo se combina con un identificador de tipo.</span><span class="sxs-lookup"><span data-stu-id="e411f-124">In the binary format, the field number is combined with a type identifier.</span></span> <span data-ttu-id="e411f-125">Los números de campo del 1 al 15 se pueden codificar con su tipo como un solo byte.</span><span class="sxs-lookup"><span data-stu-id="e411f-125">Field numbers from 1 to 15 can be encoded with their type as a single byte.</span></span> <span data-ttu-id="e411f-126">Los números de 16 a 2.047 toman 2 bytes.</span><span class="sxs-lookup"><span data-stu-id="e411f-126">Numbers from 16 to 2,047 take 2 bytes.</span></span> <span data-ttu-id="e411f-127">Puede ir más alto si necesita más de 2.047 campos en un mensaje por cualquier motivo.</span><span class="sxs-lookup"><span data-stu-id="e411f-127">You can go higher if you need more than 2,047 fields on a message for any reason.</span></span> <span data-ttu-id="e411f-128">Los identificadores de bytes únicos para los números de campo 1 a 15 ofrecen un mejor rendimiento, por lo que debe usarlos para los campos más básicos y de uso frecuente.</span><span class="sxs-lookup"><span data-stu-id="e411f-128">The single byte identifiers for field numbers 1 to 15 offer better performance, so you should use them for the most basic, frequently used fields.</span></span>

## <a name="types"></a><span data-ttu-id="e411f-129">Tipos</span><span class="sxs-lookup"><span data-stu-id="e411f-129">Types</span></span>

<span data-ttu-id="e411f-130">Las declaraciones de tipo utilizan los tipos de datos escalares nativos de Protobuf, que se describen con más detalle en [la sección siguiente.](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="e411f-130">The type declarations are using Protobuf's native scalar data types, which are discussed in more detail in [the next section](protobuf-data-types.md).</span></span> <span data-ttu-id="e411f-131">El resto de este capítulo tratará los tipos integrados de Protobuf y mostrará cómo se relacionan con los tipos comunes de .NET.</span><span class="sxs-lookup"><span data-stu-id="e411f-131">The rest of this chapter will cover Protobuf's built-in types and show how they relate to common .NET types.</span></span>

> [!NOTE]
> <span data-ttu-id="e411f-132">Protobuf no admite de `decimal` forma nativa `double` un tipo, por lo que se usa en su lugar.</span><span class="sxs-lookup"><span data-stu-id="e411f-132">Protobuf doesn't natively support a `decimal` type, so `double` is used instead.</span></span> <span data-ttu-id="e411f-133">Para aplicaciones que requieren precisión decimal completa, consulte la [sección decimal en](protobuf-data-types.md#decimals) la siguiente parte de este capítulo.</span><span class="sxs-lookup"><span data-stu-id="e411f-133">For applications that require full decimal precision, refer to the [section on decimals](protobuf-data-types.md#decimals) in the next part of this chapter.</span></span>

## <a name="the-generated-code"></a><span data-ttu-id="e411f-134">El código generado</span><span class="sxs-lookup"><span data-stu-id="e411f-134">The generated code</span></span>

<span data-ttu-id="e411f-135">Al compilar la aplicación, Protobuf crea clases para cada uno de los mensajes, asignando sus tipos nativos a tipos de C.</span><span class="sxs-lookup"><span data-stu-id="e411f-135">When you build your application, Protobuf creates classes for each of your messages, mapping its native types to C# types.</span></span> <span data-ttu-id="e411f-136">El tipo `Stock` generado tendría la siguiente firma:</span><span class="sxs-lookup"><span data-stu-id="e411f-136">The generated `Stock` type would have the following signature:</span></span>

```csharp
public class Stock
{
    public int Id { get; set; }
    public string Symbol { get; set; }
    public string DisplayName { get; set; }
    public int MarketId { get; set; }
}
```

<span data-ttu-id="e411f-137">El código real que se genera es mucho más complicado que esto.</span><span class="sxs-lookup"><span data-stu-id="e411f-137">The actual code that's generated is far more complicated than this.</span></span> <span data-ttu-id="e411f-138">La razón es que cada clase contiene todo el código necesario para serializar y deserializarse al formato de cable binario.</span><span class="sxs-lookup"><span data-stu-id="e411f-138">The reason is that each class contains all the code necessary to serialize and deserialize itself to the binary wire format.</span></span>

### <a name="property-names"></a><span data-ttu-id="e411f-139">Nombres de propiedad</span><span class="sxs-lookup"><span data-stu-id="e411f-139">Property names</span></span>

<span data-ttu-id="e411f-140">Tenga en cuenta que `PascalCase` el compilador Protobuf `snake_case` se `.proto` aplicó a los nombres de propiedad, aunque estaban en el archivo.</span><span class="sxs-lookup"><span data-stu-id="e411f-140">Note that the Protobuf compiler applied `PascalCase` to the property names, although they were `snake_case` in the `.proto` file.</span></span> <span data-ttu-id="e411f-141">La guía de estilo `snake_case` [Protobuf](https://developers.google.com/protocol-buffers/docs/style) recomienda usar en las definiciones de mensajes para que la generación de código para otras plataformas genere el caso esperado para sus convenciones.</span><span class="sxs-lookup"><span data-stu-id="e411f-141">The [Protobuf style guide](https://developers.google.com/protocol-buffers/docs/style) recommends using `snake_case` in your message definitions so that the code generation for other platforms produces the expected case for their conventions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e411f-142">[Anterior](protocol-buffers.md)
>[Siguiente](protobuf-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="e411f-142">[Previous](protocol-buffers.md)
[Next](protobuf-data-types.md)</span></span>
