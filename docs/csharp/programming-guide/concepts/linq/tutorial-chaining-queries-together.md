---
title: 'Tutorial: encadenar cadenas juntas (C#)'
ms.date: 07/20/2015
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
ms.openlocfilehash: cab012a6ae618bd731c26bc1a002c144b84d2169
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45609637"
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="3103c-102">Tutorial: encadenar cadenas juntas (C#)</span><span class="sxs-lookup"><span data-stu-id="3103c-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="3103c-103">Este tutorial ilustra el modelo de procesamiento que se usa al encadenar cadenas conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="3103c-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="3103c-104">Encadenar cadenas conjuntamente constituye una parte clave de escribir transformaciones funcionales.</span><span class="sxs-lookup"><span data-stu-id="3103c-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="3103c-105">Es importante entender exactamente cómo funciona el encadenamiento de consultas.</span><span class="sxs-lookup"><span data-stu-id="3103c-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="3103c-106">Las consultas que procesan los documentos XML abierto de Office usan esta técnica de forma intensiva.</span><span class="sxs-lookup"><span data-stu-id="3103c-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3103c-107">En esta sección</span><span class="sxs-lookup"><span data-stu-id="3103c-107">In This Section</span></span>  
  
|<span data-ttu-id="3103c-108">Tema</span><span class="sxs-lookup"><span data-stu-id="3103c-108">Topic</span></span>|<span data-ttu-id="3103c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3103c-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3103c-110">Ejecución aplazada y evaluación diferida en LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3103c-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="3103c-111">Describe los conceptos de ejecución aplazada y evaluación diferida.</span><span class="sxs-lookup"><span data-stu-id="3103c-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|<span data-ttu-id="3103c-112">[Deferred Execution Example (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md) (Ejemplo de ejecución diferida (C#))</span><span class="sxs-lookup"><span data-stu-id="3103c-112">[Deferred Execution Example (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)</span></span>|<span data-ttu-id="3103c-113">Proporciona un ejemplo de ejecución aplazada.</span><span class="sxs-lookup"><span data-stu-id="3103c-113">Provides an example of deferred execution.</span></span>|  
|<span data-ttu-id="3103c-114">[Chaining Queries Example (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md) (Ejemplo de encadenamiento de consultas (C#))</span><span class="sxs-lookup"><span data-stu-id="3103c-114">[Chaining Queries Example (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)</span></span>|<span data-ttu-id="3103c-115">Muestra cómo funciona la ejecución aplazada cuando se encadenan consultas conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="3103c-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|<span data-ttu-id="3103c-116">[Intermediate Materialization (C#)](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md) (Materialización intermedia (C#))</span><span class="sxs-lookup"><span data-stu-id="3103c-116">[Intermediate Materialization (C#)](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)</span></span>|<span data-ttu-id="3103c-117">Identifica e ilustra la semántica de la materialización intermedia.</span><span class="sxs-lookup"><span data-stu-id="3103c-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|<span data-ttu-id="3103c-118">[Chaining Standard Query Operators Together (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md) (Encadenar juntos operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="3103c-118">[Chaining Standard Query Operators Together (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)</span></span>|<span data-ttu-id="3103c-119">Describe la semántica diferida de los operadores de consulta estándar.</span><span class="sxs-lookup"><span data-stu-id="3103c-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3103c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3103c-120">See Also</span></span>

- [<span data-ttu-id="3103c-121">Transformaciones funcionales puras de XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3103c-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
