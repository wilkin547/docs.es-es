---
title: Indizadores
description: Obtenga información sobre los indexadores de C# y cómo implementan propiedades indexadas, que son propiedades a las que se hace referencia con uno o más argumentos.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: 1369740404c500d8b44b4706959bf4640c26aa2d
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656116"
---
# <a name="indexers"></a><span data-ttu-id="54273-103">Indizadores</span><span class="sxs-lookup"><span data-stu-id="54273-103">Indexers</span></span>

<span data-ttu-id="54273-104">Los *indizadores* son similares a las propiedades.</span><span class="sxs-lookup"><span data-stu-id="54273-104">*Indexers* are similar to properties.</span></span> <span data-ttu-id="54273-105">Muchas veces, los indizadores se basan en las mismas características del lenguaje que las [propiedades](properties.md).</span><span class="sxs-lookup"><span data-stu-id="54273-105">In many ways indexers build on the same language features as [properties](properties.md).</span></span> <span data-ttu-id="54273-106">Los indizadores permiten las propiedades *indizadas*: propiedades a las que se hace referencia mediante uno o más argumentos.</span><span class="sxs-lookup"><span data-stu-id="54273-106">Indexers enable *indexed* properties: properties referenced using one or more arguments.</span></span> <span data-ttu-id="54273-107">Estos argumentos proporcionan un índice en alguna colección de valores.</span><span class="sxs-lookup"><span data-stu-id="54273-107">Those arguments provide an index into some collection of values.</span></span>

## <a name="indexer-syntax"></a><span data-ttu-id="54273-108">Sintaxis del indizador</span><span class="sxs-lookup"><span data-stu-id="54273-108">Indexer Syntax</span></span>

<span data-ttu-id="54273-109">Se obtiene acceso a un indizador usando un nombre de variable y corchetes.</span><span class="sxs-lookup"><span data-stu-id="54273-109">You access an indexer through a variable name and square brackets.</span></span> <span data-ttu-id="54273-110">Los argumentos del indizador se colocan dentro de los corchetes:</span><span class="sxs-lookup"><span data-stu-id="54273-110">You place the indexer arguments inside the brackets:</span></span>

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

<span data-ttu-id="54273-111">Los indizadores se declaran con la palabra clave `this` como nombre de la propiedad y declarando los argumentos entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="54273-111">You declare indexers using the `this` keyword as the property name, and declaring the arguments within square brackets.</span></span> <span data-ttu-id="54273-112">Esta declaración coincidiría con el uso que se muestra en el párrafo anterior:</span><span class="sxs-lookup"><span data-stu-id="54273-112">This declaration would match the usage shown in the previous paragraph:</span></span>

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

<span data-ttu-id="54273-113">En este ejemplo inicial puede ver la relación existente entre la sintaxis de las propiedades y los indizadores.</span><span class="sxs-lookup"><span data-stu-id="54273-113">From this initial example, you can see the relationship between the syntax for properties and for indexers.</span></span> <span data-ttu-id="54273-114">Esta analogía lleva a cabo la mayoría de las reglas de sintaxis de los indizadores.</span><span class="sxs-lookup"><span data-stu-id="54273-114">This analogy carries through most of the syntax rules for indexers.</span></span> <span data-ttu-id="54273-115">Los indizadores pueden tener cualquier modificador de acceso válido (público, interno protegido, protegido, interno, privado o privado protegido).</span><span class="sxs-lookup"><span data-stu-id="54273-115">Indexers can have any valid access modifiers (public, protected internal, protected, internal, private or private protected).</span></span> <span data-ttu-id="54273-116">Pueden ser sellados, virtuales o abstractos.</span><span class="sxs-lookup"><span data-stu-id="54273-116">They may be sealed, virtual, or abstract.</span></span> <span data-ttu-id="54273-117">Al igual que con las propiedades, puede especificar distintos modificadores de acceso para los descriptores de acceso get y set en un indizador.</span><span class="sxs-lookup"><span data-stu-id="54273-117">As with properties, you can specify different access modifiers for the get and set accessors in an indexer.</span></span>
<span data-ttu-id="54273-118">También puede especificar indizadores de solo lectura (omitiendo el descriptor de acceso set) o indizadores de solo escritura (omitiendo el descriptor de acceso get).</span><span class="sxs-lookup"><span data-stu-id="54273-118">You may also specify read-only indexers (by omitting the set accessor), or write-only indexers (by omitting the get accessor).</span></span>

<span data-ttu-id="54273-119">Puede aplicar a los indizadores casi todo lo que aprenda al trabajar con propiedades.</span><span class="sxs-lookup"><span data-stu-id="54273-119">You can apply almost everything you learn from working with properties to indexers.</span></span> <span data-ttu-id="54273-120">La única excepción a esta regla son las *propiedades implementadas automáticamente*.</span><span class="sxs-lookup"><span data-stu-id="54273-120">The only exception to that rule is *auto implemented properties*.</span></span> <span data-ttu-id="54273-121">El compilador no siempre puede generar el almacenamiento correcto para un indizador.</span><span class="sxs-lookup"><span data-stu-id="54273-121">The compiler cannot always generate the correct storage for an indexer.</span></span>

<span data-ttu-id="54273-122">La presencia de argumentos para hacer referencia a un elemento en un conjunto de elementos distingue los indizadores de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="54273-122">The presence of arguments to reference an item in a set of items distinguishes indexers from properties.</span></span> <span data-ttu-id="54273-123">Puede definir varios indizadores en un tipo, mientras que las listas de argumentos de cada indizador son únicas.</span><span class="sxs-lookup"><span data-stu-id="54273-123">You may define multiple indexers on a type, as long as the argument lists for each indexer is unique.</span></span> <span data-ttu-id="54273-124">Vamos a explorar escenarios diferentes en los que puede usar uno o varios indizadores en una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="54273-124">Let's explore different scenarios where you might use one or more indexers in a class definition.</span></span>

## <a name="scenarios"></a><span data-ttu-id="54273-125">Escenarios</span><span class="sxs-lookup"><span data-stu-id="54273-125">Scenarios</span></span>

<span data-ttu-id="54273-126">Tendría que definir *indizadores* en el tipo si su API modela alguna colección en la que se definen los argumentos de esa colección.</span><span class="sxs-lookup"><span data-stu-id="54273-126">You would define *indexers* in your type when its API models some collection where you define the arguments to that collection.</span></span> <span data-ttu-id="54273-127">Los indizadores pueden (o no) asignarse directamente a los tipos de colección que forman parte del marco de trabajo principal de .NET.</span><span class="sxs-lookup"><span data-stu-id="54273-127">Your indexers may or may not map directly to the collection types that are part of the .NET core framework.</span></span> <span data-ttu-id="54273-128">El tipo puede tener otras responsabilidades, además de tener que modelar una colección.</span><span class="sxs-lookup"><span data-stu-id="54273-128">Your type may have other responsibilities in addition to modeling a collection.</span></span>
<span data-ttu-id="54273-129">Los indizadores le permiten proporcionar la API que coincida con la abstracción de su tipo sin tener que exponer la información interna de cómo se almacenan o se calculan los valores de dicha abstracción.</span><span class="sxs-lookup"><span data-stu-id="54273-129">Indexers enable you to provide the API that matches your type's abstraction without exposing the inner details of how the values for that abstraction are stored or computed.</span></span>

<span data-ttu-id="54273-130">Veamos algunos de los escenarios habituales en los que se usan los *indizadores*.</span><span class="sxs-lookup"><span data-stu-id="54273-130">Let's walk through some of the common scenarios for using *indexers*.</span></span> <span data-ttu-id="54273-131">Puede obtener acceso a la [carpeta de ejemplo para indexadores](https://github.com/dotnet/samples/tree/master/csharp/indexers).</span><span class="sxs-lookup"><span data-stu-id="54273-131">You can access the [sample folder for indexers](https://github.com/dotnet/samples/tree/master/csharp/indexers).</span></span> <span data-ttu-id="54273-132">Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#view-and-download-samples).</span><span class="sxs-lookup"><span data-stu-id="54273-132">For download instructions, see [Samples and Tutorials](../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

### <a name="arrays-and-vectors"></a><span data-ttu-id="54273-133">Matrices y vectores</span><span class="sxs-lookup"><span data-stu-id="54273-133">Arrays and Vectors</span></span>

<span data-ttu-id="54273-134">Uno de los escenarios más comunes para crear indizadores es cuando el tipo modela una matriz o un vector.</span><span class="sxs-lookup"><span data-stu-id="54273-134">One of the most common scenarios for creating indexers is when your type models an array, or a vector.</span></span> <span data-ttu-id="54273-135">Puede crear un indizador para modelar una lista ordenada de datos.</span><span class="sxs-lookup"><span data-stu-id="54273-135">You can create an indexer to model an ordered list of data.</span></span>

<span data-ttu-id="54273-136">La ventaja de crear su propio indizador es que puede definir el almacenamiento de esa colección para satisfacer sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="54273-136">The advantage of creating your own indexer is that you can define the storage for that collection to suit your needs.</span></span> <span data-ttu-id="54273-137">Piense en un escenario en el que el tipo modela datos históricos que tienen un tamaño demasiado grande para poder cargarlos en la memoria de una vez.</span><span class="sxs-lookup"><span data-stu-id="54273-137">Imagine a scenario where your type models historical data that is too large to load into memory at once.</span></span> <span data-ttu-id="54273-138">Debe cargar y descargar secciones de la colección en función del uso.</span><span class="sxs-lookup"><span data-stu-id="54273-138">You need to load and unload sections of the collection based on usage.</span></span> <span data-ttu-id="54273-139">En el ejemplo siguiente se modela este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="54273-139">The example following models this behavior.</span></span> <span data-ttu-id="54273-140">Informa sobre el número de puntos de datos existente,</span><span class="sxs-lookup"><span data-stu-id="54273-140">It reports on how many data points exist.</span></span> <span data-ttu-id="54273-141">crea páginas para incluir secciones de los datos a petición</span><span class="sxs-lookup"><span data-stu-id="54273-141">It creates pages to hold sections of the data on demand.</span></span> <span data-ttu-id="54273-142">y quita páginas de la memoria para dejar espacio para las páginas necesarias para las solicitudes más recientes.</span><span class="sxs-lookup"><span data-stu-id="54273-142">It removes pages from memory to make room for pages needed by more recent requests.</span></span>

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

<span data-ttu-id="54273-143">Puede seguir esta expresión de diseño para modelar cualquier tipo de colección cuando haya motivos de peso para no cargar todo el conjunto de datos en una colección en memoria.</span><span class="sxs-lookup"><span data-stu-id="54273-143">You can follow this design idiom to model any sort of collection where there are good reasons not to load the entire set of data into an in- memory collection.</span></span> <span data-ttu-id="54273-144">Observe que la clase `Page` es una clase anidada privada que no forma parte de la interfaz pública.</span><span class="sxs-lookup"><span data-stu-id="54273-144">Notice that the `Page` class is a private nested class that is not part of the public interface.</span></span> <span data-ttu-id="54273-145">Estos datos se ocultan a los usuarios de esta clase.</span><span class="sxs-lookup"><span data-stu-id="54273-145">Those details are hidden from any users of this class.</span></span>

### <a name="dictionaries"></a><span data-ttu-id="54273-146">Diccionarios</span><span class="sxs-lookup"><span data-stu-id="54273-146">Dictionaries</span></span>

<span data-ttu-id="54273-147">Otro escenario habitual es cuando necesita modelar un diccionario o una asignación.</span><span class="sxs-lookup"><span data-stu-id="54273-147">Another common scenario is when you need to model a dictionary or a map.</span></span> <span data-ttu-id="54273-148">En este escenario, el tipo almacena valores en función de la clave (normalmente claves de texto).</span><span class="sxs-lookup"><span data-stu-id="54273-148">This scenario is when your type stores values based on key, typically text keys.</span></span> <span data-ttu-id="54273-149">En este ejemplo se crea un diccionario que asigna argumentos de la línea de comandos a [expresiones lambda](delegates-overview.md) que administran estas opciones.</span><span class="sxs-lookup"><span data-stu-id="54273-149">This example creates a dictionary that maps command line arguments to [lambda expressions](delegates-overview.md) that manage those options.</span></span> <span data-ttu-id="54273-150">En el ejemplo siguiente se muestran dos clases: una clase `ArgsActions`, que asigna una opción de la línea de comandos a un delegado `Action`; y `ArgsProcessor`, que usa `ArgsActions` para ejecutar cada `Action` cuando encuentra esa opción.</span><span class="sxs-lookup"><span data-stu-id="54273-150">The following example shows two classes: an `ArgsActions` class that maps a command line option to an `Action` delegate, and an `ArgsProcessor` that uses the `ArgsActions` to execute each `Action` when it encounters that option.</span></span>

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

<span data-ttu-id="54273-151">En este ejemplo, la colección `ArgsAction` está estrechamente relacionada con la colección subyacente.</span><span class="sxs-lookup"><span data-stu-id="54273-151">In this example, the `ArgsAction` collection maps closely to the underlying collection.</span></span>
<span data-ttu-id="54273-152">`get` determina si se ha configurado una opción determinada.</span><span class="sxs-lookup"><span data-stu-id="54273-152">The `get` determines if a given option has been configured.</span></span> <span data-ttu-id="54273-153">Si es así, devuelve la `Action` asociada a esa opción.</span><span class="sxs-lookup"><span data-stu-id="54273-153">If so, it returns the `Action` associated with that option.</span></span> <span data-ttu-id="54273-154">Si no, devuelve una `Action` que no hace nada.</span><span class="sxs-lookup"><span data-stu-id="54273-154">If not, it returns an `Action` that does nothing.</span></span> <span data-ttu-id="54273-155">El descriptor de acceso público no incluye ningún descriptor de acceso `set`,</span><span class="sxs-lookup"><span data-stu-id="54273-155">The public accessor does not include a `set` accessor.</span></span> <span data-ttu-id="54273-156">sino el diseño que usa un método público para establecer opciones.</span><span class="sxs-lookup"><span data-stu-id="54273-156">Rather, the design using a public method for setting options.</span></span>

### <a name="multi-dimensional-maps"></a><span data-ttu-id="54273-157">Asignaciones multidimensionales</span><span class="sxs-lookup"><span data-stu-id="54273-157">Multi-Dimensional Maps</span></span>

<span data-ttu-id="54273-158">Puede crear indizadores que usen varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="54273-158">You can create indexers that use multiple arguments.</span></span> <span data-ttu-id="54273-159">Además, estos argumentos no se restringen para que sean del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="54273-159">In addition, those arguments are not constrained to be the same type.</span></span> <span data-ttu-id="54273-160">Veamos dos ejemplos.</span><span class="sxs-lookup"><span data-stu-id="54273-160">Let's look at two examples.</span></span>

<span data-ttu-id="54273-161">En el primer ejemplo se muestra una clase que genera valores para el conjunto Mandelbrot.</span><span class="sxs-lookup"><span data-stu-id="54273-161">The first example shows a class that generates values for a Mandelbrot set.</span></span> <span data-ttu-id="54273-162">Para obtener más información sobre las matemáticas subyacentes en el conjunto, lea [este artículo](https://en.wikipedia.org/wiki/Mandelbrot_set).</span><span class="sxs-lookup"><span data-stu-id="54273-162">For more information on the mathematics behind the set, read [this article](https://en.wikipedia.org/wiki/Mandelbrot_set).</span></span>
<span data-ttu-id="54273-163">El indizador usa dos valores double para definir un punto en el plano X, Y.</span><span class="sxs-lookup"><span data-stu-id="54273-163">The indexer uses two doubles to define a point in the X, Y plane.</span></span>
<span data-ttu-id="54273-164">El descriptor de acceso get calcula el número de iteraciones existente hasta que se determina que un punto no está en el conjunto.</span><span class="sxs-lookup"><span data-stu-id="54273-164">The get accessor computes the number of iterations until a point is determined to be not in the set.</span></span> <span data-ttu-id="54273-165">Si se alcanza el número máximo de iteraciones, el punto está en el conjunto y se devuelve el valor maxIterations de la clase</span><span class="sxs-lookup"><span data-stu-id="54273-165">If the maximum iterations is reached, the point is in the set, and the class's maxIterations value is returned.</span></span> <span data-ttu-id="54273-166">(las imágenes generadas por PC popularizadas para el conjunto Mandelbrot definen colores para el número de iteraciones que son necesarias para determinar que un punto en concreto está fuera del conjunto).</span><span class="sxs-lookup"><span data-stu-id="54273-166">(The computer generated images popularized for the Mandelbrot set define colors for the number of iterations necessary to determine that a point is outside the set.</span></span>

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

<span data-ttu-id="54273-167">El conjunto Mandelbrot define valores en cada coordenada (x o y) para los valores numéricos reales.</span><span class="sxs-lookup"><span data-stu-id="54273-167">The Mandelbrot Set defines values at every (x,y) coordinate for real number values.</span></span>
<span data-ttu-id="54273-168">Con esto se define un diccionario que puede contener un número infinito de valores.</span><span class="sxs-lookup"><span data-stu-id="54273-168">That defines a dictionary that could contain an infinite number of values.</span></span> <span data-ttu-id="54273-169">Por lo tanto, no hay ningún almacenamiento detrás del conjunto.</span><span class="sxs-lookup"><span data-stu-id="54273-169">Therefore, there is no storage behind the set.</span></span> <span data-ttu-id="54273-170">En su lugar, esta clase calcula el valor de cada punto cuando el código llama al descriptor de acceso `get`,</span><span class="sxs-lookup"><span data-stu-id="54273-170">Instead, this class computes the value for each point when code calls the `get` accessor.</span></span> <span data-ttu-id="54273-171">por lo que no se usa ningún almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="54273-171">There's no underlying storage used.</span></span>

<span data-ttu-id="54273-172">Vamos a examinar un último uso de los indizadores, en el que el indizador toma varios argumentos de distintos tipos.</span><span class="sxs-lookup"><span data-stu-id="54273-172">Let's examine one last use of indexers, where the indexer takes multiple arguments of different types.</span></span> <span data-ttu-id="54273-173">Imagínese un programa que administra datos históricos de temperaturas.</span><span class="sxs-lookup"><span data-stu-id="54273-173">Consider a program that manages historical temperature data.</span></span> <span data-ttu-id="54273-174">Este indizador usa una ciudad y una fecha para establecer u obtener las temperaturas máximas y mínimas de ese lugar:</span><span class="sxs-lookup"><span data-stu-id="54273-174">This indexer uses a city and a date to set or get the high and low temperatures for that location:</span></span>

```csharp
using DateMeasurements =
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements =
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

<span data-ttu-id="54273-175">Este ejemplo crea un indizador que asigna los datos meteorológicos en dos argumentos diferentes: una ciudad (representada por `string`) y una fecha (representada por `DateTime`).</span><span class="sxs-lookup"><span data-stu-id="54273-175">This example creates an indexer that maps weather data on two different arguments: a city (represented by a `string`) and a date (represented by a `DateTime`).</span></span> <span data-ttu-id="54273-176">El almacenamiento interno usa dos clases `Dictionary` para representar el diccionario bidimensional.</span><span class="sxs-lookup"><span data-stu-id="54273-176">The internal storage uses two `Dictionary` classes to represent the two-dimensional dictionary.</span></span> <span data-ttu-id="54273-177">La API pública ya no representa el almacenamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="54273-177">The public API no longer represents the underlying storage.</span></span> <span data-ttu-id="54273-178">En su lugar, las características del lenguaje de los indizadores le permiten crear una interfaz pública que representa la abstracción, aunque el almacenamiento subyacente debe usar distintos tipos de colección básica.</span><span class="sxs-lookup"><span data-stu-id="54273-178">Rather, the language features of indexers enables you to create a public interface that represents your abstraction, even though the underlying storage must use different core collection types.</span></span>

<span data-ttu-id="54273-179">Hay dos partes de este código que pueden resultar desconocidas para algunos desarrolladores,</span><span class="sxs-lookup"><span data-stu-id="54273-179">There are two parts of this code that may be unfamiliar to some developers.</span></span> <span data-ttu-id="54273-180">Estas dos directivas `using`:</span><span class="sxs-lookup"><span data-stu-id="54273-180">These two `using` directives:</span></span>

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

<span data-ttu-id="54273-181">Estas instrucciones crean un *alias* para un tipo genérico construido</span><span class="sxs-lookup"><span data-stu-id="54273-181">create an *alias* for a constructed generic type.</span></span> <span data-ttu-id="54273-182">y permiten que el código use después los nombres `DateMeasurements` y `CityDateMeasurements` (más descriptivos) en vez de la construcción genérica de `Dictionary<DateTime, Measurements>` y `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span><span class="sxs-lookup"><span data-stu-id="54273-182">Those statements enable the code later to use the more descriptive `DateMeasurements` and `CityDateMeasurements` names instead of the generic construction of `Dictionary<DateTime, Measurements>` and `Dictionary<string, Dictionary<DateTime, Measurements> >`.</span></span>
<span data-ttu-id="54273-183">Esta construcción requiere el uso de los nombres completos de tipo en el lado derecho del signo `=`.</span><span class="sxs-lookup"><span data-stu-id="54273-183">This construct does require using the fully qualified type names on the right side of the `=` sign.</span></span>

<span data-ttu-id="54273-184">La segunda técnica consiste en quitar las partes de tiempo de cualquier objeto `DateTime` usado para indizarse en las colecciones.</span><span class="sxs-lookup"><span data-stu-id="54273-184">The second technique is to strip off the time portions of any `DateTime` object used to index into the collections.</span></span> <span data-ttu-id="54273-185">.NET no incluye un tipo de solo fecha.</span><span class="sxs-lookup"><span data-stu-id="54273-185">.NET doesn't include a date-only type.</span></span>
<span data-ttu-id="54273-186">Los desarrolladores usan el tipo `DateTime`, aunque emplean la propiedad `Date` para asegurarse de que cualquier objeto `DateTime` de ese día sea igual.</span><span class="sxs-lookup"><span data-stu-id="54273-186">Developers use the `DateTime` type, but use the `Date` property to ensure that any `DateTime` object from that day are equal.</span></span>

## <a name="summing-up"></a><span data-ttu-id="54273-187">Resumen</span><span class="sxs-lookup"><span data-stu-id="54273-187">Summing Up</span></span>

<span data-ttu-id="54273-188">Debe crear indizadores siempre que tenga un elemento de propiedad en la clase, en la que dicha propiedad no representa un valor único, sino una serie de valores donde cada elemento se identifica mediante un conjunto de argumentos.</span><span class="sxs-lookup"><span data-stu-id="54273-188">You should create indexers anytime you have a property-like element in your class where that property represents not a single value, but rather a collection of values where each individual item is identified by a set of arguments.</span></span> <span data-ttu-id="54273-189">Estos argumentos únicamente pueden identificar el elemento al que se debe hacer referencia en la colección.</span><span class="sxs-lookup"><span data-stu-id="54273-189">Those arguments can uniquely identify which item in the collection should be referenced.</span></span>
<span data-ttu-id="54273-190">Los indizadores amplían el concepto de las [propiedades](properties.md), en las que un miembro se trata como un elemento de datos desde fuera de la clase, pero como un método desde dentro.</span><span class="sxs-lookup"><span data-stu-id="54273-190">Indexers extend the concept of [properties](properties.md), where a member is treated like a data item from outside the class, but like a method on the inside.</span></span> <span data-ttu-id="54273-191">Los indizadores permiten que los argumentos busquen un solo elemento en una propiedad que representa un conjunto de elementos.</span><span class="sxs-lookup"><span data-stu-id="54273-191">Indexers allow arguments to find a single item in a property that represents a set of items.</span></span>
