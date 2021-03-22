---
title: Programación asincrónica en C#
description: Información general sobre la compatibilidad con el lenguaje C# para la programación asincrónica mediante async, await, Task y Task<T>
ms.date: 06/04/2020
ms.openlocfilehash: ffc2289f3b5abfe3865e1a096ee91e2e649a6427
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103624245"
---
# <a name="asynchronous-programming-with-async-and-await"></a><span data-ttu-id="ce45c-103">Programación asincrónica con async y await</span><span class="sxs-lookup"><span data-stu-id="ce45c-103">Asynchronous programming with async and await</span></span>

<span data-ttu-id="ce45c-104">El [modelo de programación asincrónica de tareas (TAP)](task-asynchronous-programming-model.md) es una abstracción del código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-104">The [Task asynchronous programming model (TAP)](task-asynchronous-programming-model.md) provides an abstraction over asynchronous code.</span></span> <span data-ttu-id="ce45c-105">El código se escribe como una secuencia de instrucciones, como es habitual.</span><span class="sxs-lookup"><span data-stu-id="ce45c-105">You write code as a sequence of statements, just like always.</span></span> <span data-ttu-id="ce45c-106">Puede leerlo como si cada instrucción se completase antes de comenzar la siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-106">You can read that code as though each statement completes before the next begins.</span></span> <span data-ttu-id="ce45c-107">El compilador realiza diversas transformaciones porque algunas de estas instrucciones podrían empezar a funcionar y devolver una clase <xref:System.Threading.Tasks.Task> que representase el trabajo en curso.</span><span class="sxs-lookup"><span data-stu-id="ce45c-107">The compiler performs many transformations because some of those statements may start work and return a <xref:System.Threading.Tasks.Task> that represents the ongoing work.</span></span>

<span data-ttu-id="ce45c-108">Este es el objetivo de la sintaxis: habilitar código que se lea como una secuencia de instrucciones, pero que se ejecute siguiendo un orden mucho más complicado, en función de la asignación de recursos externos y del momento en el que se completen las tareas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-108">That's the goal of this syntax: enable code that reads like a sequence of statements, but executes in a much more complicated order based on external resource allocation and when tasks complete.</span></span> <span data-ttu-id="ce45c-109">Es similar a la manera en la que las personas dan instrucciones para los procesos que incluyen las tareas asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-109">It's analogous to how people give instructions for processes that include asynchronous tasks.</span></span> <span data-ttu-id="ce45c-110">En este artículo, usará un ejemplo con instrucciones para preparar el desayuno que le ayudará a comprender cómo las palabras clave `async` y `await` facilitan el proceso de razonar sobre el código, que incluye una serie de instrucciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-110">Throughout this article, you'll use an example of instructions for making a breakfast to see how the `async` and `await` keywords make it easier to reason about code, that includes a series of asynchronous instructions.</span></span> <span data-ttu-id="ce45c-111">Para explicar cómo se prepara un desayuno, probablemente escribirá unas instrucciones parecidas a las que se recogen en la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-111">You'd write the instructions something like the following list to explain how to make a breakfast:</span></span>

1. <span data-ttu-id="ce45c-112">Sirva una taza de café.</span><span class="sxs-lookup"><span data-stu-id="ce45c-112">Pour a cup of coffee.</span></span>
1. <span data-ttu-id="ce45c-113">Caliente una sartén y fría dos huevos.</span><span class="sxs-lookup"><span data-stu-id="ce45c-113">Heat up a pan, then fry two eggs.</span></span>
1. <span data-ttu-id="ce45c-114">Fría tres lonchas de beicon.</span><span class="sxs-lookup"><span data-stu-id="ce45c-114">Fry three slices of bacon.</span></span>
1. <span data-ttu-id="ce45c-115">Tueste dos rebanadas de pan.</span><span class="sxs-lookup"><span data-stu-id="ce45c-115">Toast two pieces of bread.</span></span>
1. <span data-ttu-id="ce45c-116">Unte el pan con mantequilla y mermelada.</span><span class="sxs-lookup"><span data-stu-id="ce45c-116">Add butter and jam to the toast.</span></span>
1. <span data-ttu-id="ce45c-117">Sirva un vaso de zumo de naranja.</span><span class="sxs-lookup"><span data-stu-id="ce45c-117">Pour a glass of orange juice.</span></span>

<span data-ttu-id="ce45c-118">Si tiene experiencia en la cocina, lo más probable es que ejecute estas instrucciones de forma **asincrónica**.</span><span class="sxs-lookup"><span data-stu-id="ce45c-118">If you have experience with cooking, you'd execute those instructions **asynchronously**.</span></span> <span data-ttu-id="ce45c-119">Primero, calentará la sartén para los huevos e irá friendo el beicon.</span><span class="sxs-lookup"><span data-stu-id="ce45c-119">You'd start warming the pan for eggs, then start the bacon.</span></span> <span data-ttu-id="ce45c-120">Después, pondrá el pan en la tostadora y empezará a freír los huevos.</span><span class="sxs-lookup"><span data-stu-id="ce45c-120">You'd put the bread in the toaster, then start the eggs.</span></span> <span data-ttu-id="ce45c-121">En cada paso del proceso, iniciará una tarea y volverá la atención a las tareas que tiene pendientes.</span><span class="sxs-lookup"><span data-stu-id="ce45c-121">At each step of the process, you'd start a task, then turn your attention to tasks that are ready for your attention.</span></span>

<span data-ttu-id="ce45c-122">La preparación del desayuno es un buen ejemplo de un trabajo asincrónico que no es paralelo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-122">Cooking breakfast is a good example of asynchronous work that isn't parallel.</span></span> <span data-ttu-id="ce45c-123">Una persona (o un subproceso) puede controlar todas estas tareas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-123">One person (or thread) can handle all these tasks.</span></span> <span data-ttu-id="ce45c-124">Siguiendo con la analogía del desayuno, una persona puede preparar el desayuno asincrónicamente si comienza la tarea siguiente antes de que finalice la anterior.</span><span class="sxs-lookup"><span data-stu-id="ce45c-124">Continuing the breakfast analogy, one person can make breakfast asynchronously by starting the next task before the first completes.</span></span> <span data-ttu-id="ce45c-125">Los alimentos se cocinan tanto si una persona supervisa el proceso como si no.</span><span class="sxs-lookup"><span data-stu-id="ce45c-125">The cooking progresses whether or not someone is watching it.</span></span> <span data-ttu-id="ce45c-126">En cuanto se empieza a calentar la sartén para los huevos, se puede comenzar a freír el beicon.</span><span class="sxs-lookup"><span data-stu-id="ce45c-126">As soon as you start warming the pan for the eggs, you can begin frying the bacon.</span></span> <span data-ttu-id="ce45c-127">Una vez que el beicon se esté haciendo, se puede poner el pan en la tostadora.</span><span class="sxs-lookup"><span data-stu-id="ce45c-127">Once the bacon starts, you can put the bread into the toaster.</span></span>

<span data-ttu-id="ce45c-128">En el caso de un algoritmo paralelo, necesitaría varios cocineros (o subprocesos).</span><span class="sxs-lookup"><span data-stu-id="ce45c-128">For a parallel algorithm, you'd need multiple cooks (or threads).</span></span> <span data-ttu-id="ce45c-129">Uno se encargaría de los huevos, otro del beicon, etc.</span><span class="sxs-lookup"><span data-stu-id="ce45c-129">One would make the eggs, one the bacon, and so on.</span></span> <span data-ttu-id="ce45c-130">Cada uno de ellos se centraría en una sola tarea.</span><span class="sxs-lookup"><span data-stu-id="ce45c-130">Each one would be focused on just that one task.</span></span> <span data-ttu-id="ce45c-131">Un cocinero (o subproceso) se bloqueará al esperar asincrónicamente a que el beicon se dore para darle la vuelta, o al esperar a que las tostadas estén listas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-131">Each cook (or thread) would be blocked synchronously waiting for bacon to be ready to flip, or the toast to pop.</span></span>

<span data-ttu-id="ce45c-132">Piense ahora en estas mismas instrucciones escritas como instrucciones de C#:</span><span class="sxs-lookup"><span data-stu-id="ce45c-132">Now, consider those same instructions written as C# statements:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-starter/Program.cs" highlight="8-27":::

:::image type="content" source="media/synchronous-breakfast.png" alt-text="Desayuno sincrónico":::

<span data-ttu-id="ce45c-134">El desayuno preparado de forma sincrónica tardó unos 30 minutos porque el total es la suma de cada tarea individual.</span><span class="sxs-lookup"><span data-stu-id="ce45c-134">The synchronously prepared breakfast, took roughly 30 minutes because the total is the sum of each individual task.</span></span>

> [!NOTE]
> <span data-ttu-id="ce45c-135">Las clases `Coffee`, `Egg`, `Bacon`, `Toast` y `Juice` están vacías.</span><span class="sxs-lookup"><span data-stu-id="ce45c-135">The `Coffee`, `Egg`, `Bacon`, `Toast`, and `Juice` classes are empty.</span></span> <span data-ttu-id="ce45c-136">Simplemente son clases de marcador creadas para la demostración; no contienen propiedades y no sirven para ningún otro propósito.</span><span class="sxs-lookup"><span data-stu-id="ce45c-136">They are simply marker classes for the purpose of demonstration, contain no properties, and serve no other purpose.</span></span>

<span data-ttu-id="ce45c-137">Los equipos no interpretan estas instrucciones de la misma manera que las personas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-137">Computers don't interpret those instructions the same way people do.</span></span> <span data-ttu-id="ce45c-138">El equipo se bloqueará en cada instrucción hasta que el trabajo se complete antes de pasar a la instrucción siguiente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-138">The computer will block on each statement until the work is complete before moving on to the next statement.</span></span> <span data-ttu-id="ce45c-139">Podría decirse que esto da lugar a un desayuno poco satisfactorio.</span><span class="sxs-lookup"><span data-stu-id="ce45c-139">That creates an unsatisfying breakfast.</span></span> <span data-ttu-id="ce45c-140">Las tareas posteriores no se pueden iniciar mientras no se completen las anteriores.</span><span class="sxs-lookup"><span data-stu-id="ce45c-140">The later tasks wouldn't be started until the earlier tasks had completed.</span></span> <span data-ttu-id="ce45c-141">Así pues, se tardará mucho más en preparar el desayuno y algunos alimentos se habrán enfriado incluso antes de servirse.</span><span class="sxs-lookup"><span data-stu-id="ce45c-141">It would take much longer to create the breakfast, and some items would have gotten cold before being served.</span></span>

<span data-ttu-id="ce45c-142">Si quiere que el equipo ejecute las instrucciones anteriores de forma asincrónica, debe escribir código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-142">If you want the computer to execute the above instructions asynchronously, you must write asynchronous code.</span></span>

<span data-ttu-id="ce45c-143">Estas cuestiones son importantes para los programas que se escriben hoy en día.</span><span class="sxs-lookup"><span data-stu-id="ce45c-143">These concerns are important for the programs you write today.</span></span> <span data-ttu-id="ce45c-144">Al escribir programas cliente, le interesa que la interfaz de usuario responda a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="ce45c-144">When you write client programs, you want the UI to be responsive to user input.</span></span> <span data-ttu-id="ce45c-145">La aplicación no debería hacer que un teléfono parezca congelado mientras descarga datos de la Web.</span><span class="sxs-lookup"><span data-stu-id="ce45c-145">Your application shouldn't make a phone appear frozen while it's downloading data from the web.</span></span> <span data-ttu-id="ce45c-146">Al escribir programas de servidor, no le conviene que los subprocesos se bloqueen.</span><span class="sxs-lookup"><span data-stu-id="ce45c-146">When you write server programs, you don't want threads blocked.</span></span> <span data-ttu-id="ce45c-147">La intención es que puedan atender también otras solicitudes.</span><span class="sxs-lookup"><span data-stu-id="ce45c-147">Those threads could be serving other requests.</span></span> <span data-ttu-id="ce45c-148">El uso de código sincrónico cuando existen alternativas asincrónicas va en detrimento de la capacidad de escalar horizontalmente a un menor coste.</span><span class="sxs-lookup"><span data-stu-id="ce45c-148">Using synchronous code when asynchronous alternatives exist hurts your ability to scale out less expensively.</span></span> <span data-ttu-id="ce45c-149">Al final, los subprocesos bloqueados pasarán factura.</span><span class="sxs-lookup"><span data-stu-id="ce45c-149">You pay for those blocked threads.</span></span>

<span data-ttu-id="ce45c-150">Las aplicaciones modernas de más éxito requieren código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-150">Successful modern applications require asynchronous code.</span></span> <span data-ttu-id="ce45c-151">Sin la compatibilidad con los lenguajes, la escritura de código asincrónico requería devoluciones de llamada, eventos de finalización u otros medios que impedían ver claramente la intención original del código.</span><span class="sxs-lookup"><span data-stu-id="ce45c-151">Without language support, writing asynchronous code required callbacks, completion events, or other means that obscured the original intent of the code.</span></span> <span data-ttu-id="ce45c-152">La ventaja del código sincrónico es que las acciones paso a paso facilitan el análisis y la comprensión.</span><span class="sxs-lookup"><span data-stu-id="ce45c-152">The advantage of the synchronous code is that its step-by-step actions make it easy to scan and understand.</span></span> <span data-ttu-id="ce45c-153">Los modelos asincrónicos tradicionales obligaban a centrarse en la naturaleza asincrónica del código, no en las acciones fundamentales.</span><span class="sxs-lookup"><span data-stu-id="ce45c-153">Traditional asynchronous models forced you to focus on the asynchronous nature of the code, not on the fundamental actions of the code.</span></span>

## <a name="dont-block-await-instead"></a><span data-ttu-id="ce45c-154">Uso de await para evitar los bloqueos</span><span class="sxs-lookup"><span data-stu-id="ce45c-154">Don't block, await instead</span></span>

<span data-ttu-id="ce45c-155">El código anterior muestra una práctica incorrecta, que consiste en construir código sincrónico para llevar a cabo operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-155">The preceding code demonstrates a bad practice: constructing synchronous code to perform asynchronous operations.</span></span> <span data-ttu-id="ce45c-156">Tal como está escrito, este código bloquea el subproceso que lo ejecuta y le impide realizar cualquier otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-156">As written, this code blocks the thread executing it from doing any other work.</span></span> <span data-ttu-id="ce45c-157">Nada lo interrumpirá mientras alguna de las tareas esté en curso.</span><span class="sxs-lookup"><span data-stu-id="ce45c-157">It won't be interrupted while any of the tasks are in progress.</span></span> <span data-ttu-id="ce45c-158">Es como si usted se quedara mirando la tostadora después de meter el pan</span><span class="sxs-lookup"><span data-stu-id="ce45c-158">It would be as though you stared at the toaster after putting the bread in.</span></span> <span data-ttu-id="ce45c-159">y no pudiera oír a nadie que le dirigiera la palabra hasta que las tostadas estuvieran listas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-159">You'd ignore anyone talking to you until the toast popped.</span></span>

<span data-ttu-id="ce45c-160">Empecemos por actualizar este código para que el subproceso no se bloquee mientras se ejecutan las tareas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-160">Let's start by updating this code so that the thread doesn't block while tasks are running.</span></span> <span data-ttu-id="ce45c-161">La palabra clave `await` proporciona un modo sin bloqueo para iniciar una tarea y, después, proseguir la ejecución cuando dicha tarea se complete.</span><span class="sxs-lookup"><span data-stu-id="ce45c-161">The `await` keyword provides a non-blocking way to start a task, then continue execution when that task completes.</span></span> <span data-ttu-id="ce45c-162">Una versión asincrónica sencilla del código para preparar el desayuno tendría un aspecto parecido al del fragmento siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-162">A simple asynchronous version of the make a breakfast code would look like the following snippet:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V2/Program.cs" ID="SnippetMain":::

> [!IMPORTANT]
> <span data-ttu-id="ce45c-163">El tiempo total transcurrido es aproximadamente el mismo que el de la versión inicial sincrónica.</span><span class="sxs-lookup"><span data-stu-id="ce45c-163">The total elapsed time is roughly the same as the initial synchronous version.</span></span> <span data-ttu-id="ce45c-164">El código todavía tiene que aprovechar algunas de las características clave de la programación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ce45c-164">The code has yet to take advantage of some of the key features of asynchronous programming.</span></span>

> [!TIP]
> <span data-ttu-id="ce45c-165">Los cuerpos del método de `FryEggsAsync`, `FryBaconAsync` y `ToastBreadAsync` se han actualizado para devolver `Task<Egg>`, `Task<Bacon>` y `Task<Toast>`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-165">The method bodies of the `FryEggsAsync`, `FryBaconAsync`, and `ToastBreadAsync` have all been updated to return `Task<Egg>`, `Task<Bacon>`, and `Task<Toast>` respectively.</span></span> <span data-ttu-id="ce45c-166">Se cambia el nombre de los métodos de su versión original para incluir el sufijo "Async".</span><span class="sxs-lookup"><span data-stu-id="ce45c-166">The methods are renamed from their original version to include the "Async" suffix.</span></span> <span data-ttu-id="ce45c-167">Sus implementaciones se muestran como parte de la [versión final](#final-version) más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-167">Their implementations are shown as part of the [final version](#final-version) later in this article.</span></span>

<span data-ttu-id="ce45c-168">Este código no produce un bloqueo mientras se cocinan los huevos o el beicon,</span><span class="sxs-lookup"><span data-stu-id="ce45c-168">This code doesn't block while the eggs or the bacon are cooking.</span></span> <span data-ttu-id="ce45c-169">pero tampoco inicia otras tareas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-169">This code won't start any other tasks though.</span></span> <span data-ttu-id="ce45c-170">Es decir, pondría el pan en la tostadora y se quedaría esperando a que estuviera listo,</span><span class="sxs-lookup"><span data-stu-id="ce45c-170">You'd still put the toast in the toaster and stare at it until it pops.</span></span> <span data-ttu-id="ce45c-171">pero, por lo menos, si alguien reclamara su atención, le haría caso.</span><span class="sxs-lookup"><span data-stu-id="ce45c-171">But at least, you'd respond to anyone that wanted your attention.</span></span> <span data-ttu-id="ce45c-172">En un restaurante en el que se atienden varios pedidos, el cocinero empezaría a preparar otro desayuno mientras se hace el primero.</span><span class="sxs-lookup"><span data-stu-id="ce45c-172">In a restaurant where multiple orders are placed, the cook could start another breakfast while the first is cooking.</span></span>

<span data-ttu-id="ce45c-173">El subproceso que se encarga del desayuno ya no se bloquearía mientras espera por las tareas iniciadas que aún no han terminado.</span><span class="sxs-lookup"><span data-stu-id="ce45c-173">Now, the thread working on the breakfast isn't blocked while awaiting any started task that hasn't yet finished.</span></span> <span data-ttu-id="ce45c-174">En algunas aplicaciones, lo único que se necesita es este cambio.</span><span class="sxs-lookup"><span data-stu-id="ce45c-174">For some applications, this change is all that's needed.</span></span> <span data-ttu-id="ce45c-175">Una aplicación de interfaz gráfica de usuario seguirá respondiendo al usuario con este único cambio.</span><span class="sxs-lookup"><span data-stu-id="ce45c-175">A GUI application still responds to the user with just this change.</span></span> <span data-ttu-id="ce45c-176">Aun así, para este escenario, necesita algo más.</span><span class="sxs-lookup"><span data-stu-id="ce45c-176">However, for this scenario, you want more.</span></span> <span data-ttu-id="ce45c-177">No le interesa que todas las tareas de componente se ejecuten secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-177">You don't want each of the component tasks to be executed sequentially.</span></span> <span data-ttu-id="ce45c-178">Es mejor iniciar cada una de estas tareas sin esperar a que la tarea anterior se complete.</span><span class="sxs-lookup"><span data-stu-id="ce45c-178">It's better to start each of the component tasks before awaiting the previous task's completion.</span></span>

## <a name="start-tasks-concurrently"></a><span data-ttu-id="ce45c-179">Inicio simultáneo de tareas</span><span class="sxs-lookup"><span data-stu-id="ce45c-179">Start tasks concurrently</span></span>

<span data-ttu-id="ce45c-180">En muchos escenarios, necesita iniciar varias tareas independientes de inmediato.</span><span class="sxs-lookup"><span data-stu-id="ce45c-180">In many scenarios, you want to start several independent tasks immediately.</span></span> <span data-ttu-id="ce45c-181">Después, a medida que finalice cada tarea, podrá seguir con el trabajo que esté listo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-181">Then, as each task finishes, you can continue other work that's ready.</span></span> <span data-ttu-id="ce45c-182">Siguiendo con la analogía del desayuno, esta es la manera más rápida de prepararlo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-182">In the breakfast analogy, that's how you get breakfast done more quickly.</span></span> <span data-ttu-id="ce45c-183">Además, de este modo, todo estará listo aproximadamente en el mismo momento.</span><span class="sxs-lookup"><span data-stu-id="ce45c-183">You also get everything done close to the same time.</span></span> <span data-ttu-id="ce45c-184">Así podrá disfrutar de un desayuno caliente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-184">You'll get a hot breakfast.</span></span>

<span data-ttu-id="ce45c-185">La clase <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> y los tipos relacionados se pueden usar para razonar sobre las tareas que están en curso.</span><span class="sxs-lookup"><span data-stu-id="ce45c-185">The <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> and related types are classes you can use to reason about tasks that are in progress.</span></span> <span data-ttu-id="ce45c-186">Esto le permite escribir código que se asemeje más a la manera en que realmente se prepara el desayuno.</span><span class="sxs-lookup"><span data-stu-id="ce45c-186">That enables you to write code that more closely resembles the way you'd actually create breakfast.</span></span> <span data-ttu-id="ce45c-187">Para ello, cocinará los huevos, el beicon y las tostadas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-187">You'd start cooking the eggs, bacon, and toast at the same time.</span></span> <span data-ttu-id="ce45c-188">Como cada uno de estos elementos requiere una acción, se ocupará de esa tarea, se encargará de la acción siguiente y esperará por todo lo que necesite su atención.</span><span class="sxs-lookup"><span data-stu-id="ce45c-188">As each requires action, you'd turn your attention to that task, take care of the next action, then await for something else that requires your attention.</span></span>

<span data-ttu-id="ce45c-189">Comenzará una tarea y conservará el objeto <xref:System.Threading.Tasks.Task> que representa el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-189">You start a task and hold on to the <xref:System.Threading.Tasks.Task> object that represents the work.</span></span> <span data-ttu-id="ce45c-190">Llevará a cabo una instrucción `await` para esperar por cada tarea antes de trabajar con su resultado.</span><span class="sxs-lookup"><span data-stu-id="ce45c-190">You'll `await` each task before working with its result.</span></span>

<span data-ttu-id="ce45c-191">Realicemos estos cambios en el código del desayuno.</span><span class="sxs-lookup"><span data-stu-id="ce45c-191">Let's make these changes to the breakfast code.</span></span> <span data-ttu-id="ce45c-192">El primer paso consiste en almacenar las tareas de las operaciones cuando se inician, en lugar de esperar por ellas:</span><span class="sxs-lookup"><span data-stu-id="ce45c-192">The first step is to store the tasks for operations when they start, rather than awaiting them:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");

Task<Bacon> baconTask = FryBaconAsync(3);
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Task<Toast> toastTask = ToastBreadAsync(2);
Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");

Juice oj = PourOJ();
Console.WriteLine("oj is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="ce45c-193">Después, puede mover las instrucciones `await` del beicon y los huevos al final del método, antes de servir el desayuno:</span><span class="sxs-lookup"><span data-stu-id="ce45c-193">Next, you can move the `await` statements for the bacon and eggs to the end of the method, before serving breakfast:</span></span>

```csharp
Coffee cup = PourCoffee();
Console.WriteLine("coffee is ready");

Task<Egg> eggsTask = FryEggsAsync(2);
Task<Bacon> baconTask = FryBaconAsync(3);
Task<Toast> toastTask = ToastBreadAsync(2);

Toast toast = await toastTask;
ApplyButter(toast);
ApplyJam(toast);
Console.WriteLine("toast is ready");
Juice oj = PourOJ();
Console.WriteLine("oj is ready");

Egg eggs = await eggsTask;
Console.WriteLine("eggs are ready");
Bacon bacon = await baconTask;
Console.WriteLine("bacon is ready");

Console.WriteLine("Breakfast is ready!");
```

:::image type="content" source="media/asynchronous-breakfast.png" alt-text="Desayuno asincrónico":::

<span data-ttu-id="ce45c-195">La preparación del desayuno de forma asincrónica apenas tomó 20 minutos, lo cual supone un ahorro de tiempo que se debe a que algunas tareas se efectuaron simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-195">The asynchronously prepared breakfast took roughly 20 minutes, this time savings is because some tasks ran concurrently.</span></span>

<span data-ttu-id="ce45c-196">El código anterior funciona mejor.</span><span class="sxs-lookup"><span data-stu-id="ce45c-196">The preceding code works better.</span></span> <span data-ttu-id="ce45c-197">Iniciará todas las tareas asincrónicas a la vez</span><span class="sxs-lookup"><span data-stu-id="ce45c-197">You start all the asynchronous tasks at once.</span></span> <span data-ttu-id="ce45c-198">y esperará por una tarea solo cuando necesite los resultados.</span><span class="sxs-lookup"><span data-stu-id="ce45c-198">You await each task only when you need the results.</span></span> <span data-ttu-id="ce45c-199">El código anterior se parece al código de una aplicación web que realiza solicitudes a diferentes microservicios y, después, combina los resultados en una sola página.</span><span class="sxs-lookup"><span data-stu-id="ce45c-199">The preceding code may be similar to code in a web application that makes requests of different microservices, then combines the results into a single page.</span></span> <span data-ttu-id="ce45c-200">Podrá realizar todas las solicitudes de inmediato y, luego, llevará a cabo una instrucción `await` para esperar por todas esas tareas y componer la página web.</span><span class="sxs-lookup"><span data-stu-id="ce45c-200">You'll make all the requests immediately, then `await` all those tasks and compose the web page.</span></span>

## <a name="composition-with-tasks"></a><span data-ttu-id="ce45c-201">Composición con tareas</span><span class="sxs-lookup"><span data-stu-id="ce45c-201">Composition with tasks</span></span>

 <span data-ttu-id="ce45c-202">Ya tiene todo listo al mismo tiempo para el desayuno, excepto las tostadas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-202">You have everything ready for breakfast at the same time except the toast.</span></span> <span data-ttu-id="ce45c-203">La preparación de las tostadas es la composición de una operación asincrónica (tostar el pan) y varias operaciones sincrónicas (untar la mantequilla y la mermelada).</span><span class="sxs-lookup"><span data-stu-id="ce45c-203">Making the toast is the composition of an asynchronous operation (toasting the bread), and synchronous operations (adding the butter and the jam).</span></span> <span data-ttu-id="ce45c-204">La actualización de este código ilustra un concepto importante:</span><span class="sxs-lookup"><span data-stu-id="ce45c-204">Updating this code illustrates an important concept:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce45c-205">La composición de una operación asincrónica seguida de un trabajo sincrónico es una operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ce45c-205">The composition of an asynchronous operation followed by synchronous work is an asynchronous operation.</span></span> <span data-ttu-id="ce45c-206">Dicho de otra manera, si una parte cualquiera de una operación es asincrónica, toda la operación es asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ce45c-206">Stated another way, if any portion of an operation is asynchronous, the entire operation is asynchronous.</span></span>

<span data-ttu-id="ce45c-207">En el código anterior se muestra que se puede usar un objeto <xref:System.Threading.Tasks.Task> o <xref:System.Threading.Tasks.Task%601> para conservar tareas en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ce45c-207">The preceding code showed you that you can use <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601> objects to hold running tasks.</span></span> <span data-ttu-id="ce45c-208">Lleva a cabo una instrucción `await` para esperar por una tarea a fin de poder usar su resultado.</span><span class="sxs-lookup"><span data-stu-id="ce45c-208">You `await` each task before using its result.</span></span> <span data-ttu-id="ce45c-209">El siguiente paso consiste en crear métodos que representan la combinación de otro trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-209">The next step is to create methods that represent the combination of other work.</span></span> <span data-ttu-id="ce45c-210">Antes de servir el desayuno, quiere esperar por la tarea que representa tostar el pan antes de untar la mantequilla y la mermelada.</span><span class="sxs-lookup"><span data-stu-id="ce45c-210">Before serving breakfast, you want to await the task that represents toasting the bread before adding butter and jam.</span></span> <span data-ttu-id="ce45c-211">Puede representar este trabajo con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-211">You can represent that work with the following code:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" ID="SnippetComposeToastTask":::

<span data-ttu-id="ce45c-212">El método anterior tiene el modificador `async` en su firma,</span><span class="sxs-lookup"><span data-stu-id="ce45c-212">The preceding method has the `async` modifier in its signature.</span></span> <span data-ttu-id="ce45c-213">lo que indica al compilador que este método incluye una instrucción `await`, es decir, que contiene operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-213">That signals to the compiler that this method contains an `await` statement; it contains asynchronous operations.</span></span> <span data-ttu-id="ce45c-214">Este método representa la tarea que tuesta el pan y, después, agrega la mantequilla y la mermelada.</span><span class="sxs-lookup"><span data-stu-id="ce45c-214">This method represents the task that toasts the bread, then adds butter and jam.</span></span> <span data-ttu-id="ce45c-215">El método devuelve un objeto <xref:System.Threading.Tasks.Task%601> que representa la composición de estas tres operaciones.</span><span class="sxs-lookup"><span data-stu-id="ce45c-215">This method returns a <xref:System.Threading.Tasks.Task%601> that represents the composition of those three operations.</span></span> <span data-ttu-id="ce45c-216">El bloque principal de código se convierte en lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-216">The main block of code now becomes:</span></span>

:::code language="csharp" source="snippets/index/AsyncBreakfast-V3/Program.cs" ID="SnippetMain":::

<span data-ttu-id="ce45c-217">El cambio anterior ilustra una técnica importante para trabajar con código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-217">The previous change illustrated an important technique for working with asynchronous code.</span></span> <span data-ttu-id="ce45c-218">Para componer tareas, las operaciones se separan en un método nuevo que devuelve una tarea.</span><span class="sxs-lookup"><span data-stu-id="ce45c-218">You compose tasks by separating the operations into a new method that returns a task.</span></span> <span data-ttu-id="ce45c-219">Usted puede elegir cuándo se debe esperar por esta tarea</span><span class="sxs-lookup"><span data-stu-id="ce45c-219">You can choose when to await that task.</span></span> <span data-ttu-id="ce45c-220">y puede iniciar otras tareas simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-220">You can start other tasks concurrently.</span></span>

## <a name="asynchronous-exceptions"></a><span data-ttu-id="ce45c-221">Excepciones asincrónicas</span><span class="sxs-lookup"><span data-stu-id="ce45c-221">Asynchronous exceptions</span></span>

<span data-ttu-id="ce45c-222">Hasta este momento, ha asumido implícitamente que todas estas tareas se completan correctamente.</span><span class="sxs-lookup"><span data-stu-id="ce45c-222">Up to this point, you've implicitly assumed that all these tasks complete successfully.</span></span> <span data-ttu-id="ce45c-223">Los métodos asincrónicos generan excepciones, al igual que sus homólogos sincrónicos.</span><span class="sxs-lookup"><span data-stu-id="ce45c-223">Asynchronous methods throw exceptions, just like their synchronous counterparts.</span></span> <span data-ttu-id="ce45c-224">La compatibilidad asincrónica con la administración de excepciones y errores presenta los mismos objetivos en general: escribir código que se lea como una serie de instrucciones sincrónicas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-224">Asynchronous support for exceptions and error handling strives for the same goals as asynchronous support in general: You should write code that reads like a series of synchronous statements.</span></span> <span data-ttu-id="ce45c-225">Las tareas, cuando no se pueden completar correctamente, generan excepciones.</span><span class="sxs-lookup"><span data-stu-id="ce45c-225">Tasks throw exceptions when they can't complete successfully.</span></span> <span data-ttu-id="ce45c-226">El código cliente puede capturar dichas excepciones cuando una tarea presenta el elemento `awaited`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-226">The client code can catch those exceptions when a started task is `awaited`.</span></span> <span data-ttu-id="ce45c-227">Por ejemplo, supongamos que, al hacer una tostada, la tostadora empieza a arder.</span><span class="sxs-lookup"><span data-stu-id="ce45c-227">For example, let's assume that the toaster catches fire while making the toast.</span></span> <span data-ttu-id="ce45c-228">Para simular esta situación, puede modificar el método `ToastBreadAsync` para que coincida con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-228">You can simulate that by modifying the `ToastBreadAsync` method to match the following code:</span></span>

```csharp
private static async Task<Toast> ToastBreadAsync(int slices)
{
    for (int slice = 0; slice < slices; slice++)
    {
        Console.WriteLine("Putting a slice of bread in the toaster");
    }
    Console.WriteLine("Start toasting...");
    await Task.Delay(2000);
    Console.WriteLine("Fire! Toast is ruined!");
    throw new InvalidOperationException("The toaster is on fire");
    await Task.Delay(1000);
    Console.WriteLine("Remove toast from toaster");

    return new Toast();
}
```

> [!NOTE]
> <span data-ttu-id="ce45c-229">Al compilar el código anterior, recibirá una advertencia referente a código inaccesible.</span><span class="sxs-lookup"><span data-stu-id="ce45c-229">You'll get a warning when you compile the preceding code regarding unreachable code.</span></span> <span data-ttu-id="ce45c-230">Es algo intencionado, porque, una vez que la tostadora empiece a arder, la actividad no se podrá llevar a cabo con normalidad.</span><span class="sxs-lookup"><span data-stu-id="ce45c-230">That's intentional, because once the toaster catches fire, operations won't proceed normally.</span></span>

<span data-ttu-id="ce45c-231">Ejecute la aplicación tras efectuar dichos cambios, con una salida similar al texto siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-231">Run the application after making these changes, and you'll output similar to the following text:</span></span>

```console
Pouring coffee
coffee is ready
Warming the egg pan...
putting 3 slices of bacon in the pan
cooking first side of bacon...
Putting a slice of bread in the toaster
Putting a slice of bread in the toaster
Start toasting...
Fire! Toast is ruined!
flipping a slice of bacon
flipping a slice of bacon
flipping a slice of bacon
cooking the second side of bacon...
cracking 2 eggs
cooking the eggs ...
Put bacon on plate
Put eggs on plate
eggs are ready
bacon is ready
Unhandled exception. System.InvalidOperationException: The toaster is on fire
   at AsyncBreakfast.Program.ToastBreadAsync(Int32 slices) in Program.cs:line 65
   at AsyncBreakfast.Program.MakeToastWithButterAndJamAsync(Int32 number) in Program.cs:line 36
   at AsyncBreakfast.Program.Main(String[] args) in Program.cs:line 24
   at AsyncBreakfast.Program.<Main>(String[] args)
```

<span data-ttu-id="ce45c-232">Observe que hay unas cuantas tareas que se completan entre que la tostadora empieza a arder y se genera la excepción.</span><span class="sxs-lookup"><span data-stu-id="ce45c-232">Notice that there's quite a few tasks completing between when the toaster catches fire and the exception is observed.</span></span> <span data-ttu-id="ce45c-233">Cuando una tarea que se ejecuta de forma asincrónica genera una excepción, esta tarea pasa a ser ***errónea***.</span><span class="sxs-lookup"><span data-stu-id="ce45c-233">When a task that runs asynchronously throws an exception, that Task is ***faulted***.</span></span> <span data-ttu-id="ce45c-234">El objeto de la tarea contiene la excepción generada en la propiedad <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce45c-234">The Task object holds the exception thrown in the <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ce45c-235">Las tareas erróneas, al encontrarse en espera, generan una excepción.</span><span class="sxs-lookup"><span data-stu-id="ce45c-235">Faulted tasks throw an exception when they're awaited.</span></span>

<span data-ttu-id="ce45c-236">Hay dos mecanismos importantes que es necesario entender: el modo en el que una excepción se almacena en una tarea errónea, y el modo en el que una excepción se desempaqueta y se vuelve a generar cuando el código espera una tarea errónea.</span><span class="sxs-lookup"><span data-stu-id="ce45c-236">There are two important mechanisms to understand: how an exception is stored in a faulted task, and how an exception is unpackaged and rethrown when code awaits a faulted task.</span></span>

<span data-ttu-id="ce45c-237">Si el código se ejecuta de forma asincrónica y genera una excepción, dicha excepción se almacena en `Task`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-237">When code running asynchronously throws an exception, that exception is stored in the `Task`.</span></span> <span data-ttu-id="ce45c-238">La propiedad <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> es un elemento <xref:System.AggregateException?displayProperty=nameWithType> porque es posible que se genere más de una excepción durante un trabajo asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-238">The <xref:System.Threading.Tasks.Task.Exception?displayProperty=nameWithType> property is an <xref:System.AggregateException?displayProperty=nameWithType> because more than one exception may be thrown during asynchronous work.</span></span> <span data-ttu-id="ce45c-239">Toda excepción generada se agrega a la colección <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce45c-239">Any exception thrown is added to the <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="ce45c-240">Si dicha propiedad `Exception` es NULL, se crea `AggregateException` y la excepción generada es el primer elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="ce45c-240">If that `Exception` property is null, a new `AggregateException` is created and the thrown exception is the first item in the collection.</span></span>

<span data-ttu-id="ce45c-241">En el caso de una tarea errónea, el escenario más habitual es que la propiedad `Exception` contenga exactamente una excepción.</span><span class="sxs-lookup"><span data-stu-id="ce45c-241">The most common scenario for a faulted task is that the `Exception` property contains exactly one exception.</span></span> <span data-ttu-id="ce45c-242">Si el código contempla un elemento `awaits` relativo a una tarea errónea, la primera excepción de la colección <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> se vuelve a generar.</span><span class="sxs-lookup"><span data-stu-id="ce45c-242">When code `awaits` a faulted task, the first exception in the <xref:System.AggregateException.InnerExceptions?displayProperty=nameWithType> collection is rethrown.</span></span> <span data-ttu-id="ce45c-243">Ese es el motivo por el que la salida de este ejemplo muestra un elemento `InvalidOperationException`, en lugar de `AggregateException`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-243">That's why the output from this example shows an `InvalidOperationException` instead of an `AggregateException`.</span></span> <span data-ttu-id="ce45c-244">El hecho de extraer la primera excepción interna hace que trabajar con métodos asincrónicos sea lo más similar posible a trabajar con sus homólogos sincrónicos.</span><span class="sxs-lookup"><span data-stu-id="ce45c-244">Extracting the first inner exception makes working with asynchronous methods as similar as possible to working with their synchronous counterparts.</span></span> <span data-ttu-id="ce45c-245">Si en su caso se generan varias excepciones, puede examinar la propiedad `Exception` del código.</span><span class="sxs-lookup"><span data-stu-id="ce45c-245">You can examine the `Exception` property in your code when your scenario may generate multiple exceptions.</span></span>

<span data-ttu-id="ce45c-246">Antes de continuar, comente estas dos líneas de su método `ToastBreadAsync`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-246">Before going on, comment out these two lines in your `ToastBreadAsync` method.</span></span> <span data-ttu-id="ce45c-247">No quiere que arda nada más:</span><span class="sxs-lookup"><span data-stu-id="ce45c-247">You don't want to start another fire:</span></span>

```csharp
Console.WriteLine("Fire! Toast is ruined!");
throw new InvalidOperationException("The toaster is on fire");
```

## <a name="await-tasks-efficiently"></a><span data-ttu-id="ce45c-248">Espera de la finalización de las tareas de forma eficaz</span><span class="sxs-lookup"><span data-stu-id="ce45c-248">Await tasks efficiently</span></span>

<span data-ttu-id="ce45c-249">La serie de instrucciones `await` al final del código anterior se puede mejorar mediante el uso de métodos de la clase `Task`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-249">The series of `await` statements at the end of the preceding code can be improved by using methods of the `Task` class.</span></span> <span data-ttu-id="ce45c-250">Una de estas API es <xref:System.Threading.Tasks.Task.WhenAll%2A>, que devuelve un objeto <xref:System.Threading.Tasks.Task> que se completa cuando finalizan todas las tareas de la lista de argumentos, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ce45c-250">One of those APIs is <xref:System.Threading.Tasks.Task.WhenAll%2A>, which returns a <xref:System.Threading.Tasks.Task> that completes when all the tasks in its argument list have completed, as shown in the following code:</span></span>

```csharp
await Task.WhenAll(eggsTask, baconTask, toastTask);
Console.WriteLine("eggs are ready");
Console.WriteLine("bacon is ready");
Console.WriteLine("toast is ready");
Console.WriteLine("Breakfast is ready!");
```

<span data-ttu-id="ce45c-251">Otra opción consiste en usar <xref:System.Threading.Tasks.Task.WhenAny%2A>, que devuelve un objeto `Task<Task>` que se completa cuando finaliza cualquiera de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="ce45c-251">Another option is to use <xref:System.Threading.Tasks.Task.WhenAny%2A>, which returns a `Task<Task>` that completes when any of its arguments completes.</span></span> <span data-ttu-id="ce45c-252">Puede esperar por la tarea devuelta, con la certeza de saber que ya ha terminado.</span><span class="sxs-lookup"><span data-stu-id="ce45c-252">You can await the returned task, knowing that it has already finished.</span></span> <span data-ttu-id="ce45c-253">En el código siguiente se muestra cómo se puede usar <xref:System.Threading.Tasks.Task.WhenAny%2A> para esperar a que la primera tarea finalice y, después, procesar su resultado.</span><span class="sxs-lookup"><span data-stu-id="ce45c-253">The following code shows how you could use <xref:System.Threading.Tasks.Task.WhenAny%2A> to await the first task to finish and then process its result.</span></span> <span data-ttu-id="ce45c-254">Después de procesar el resultado de la tarea completada, quítela de la lista de tareas que se pasan a `WhenAny`.</span><span class="sxs-lookup"><span data-stu-id="ce45c-254">After processing the result from the completed task, you remove that completed task from the list of tasks passed to `WhenAny`.</span></span>

```csharp
var breakfastTasks = new List<Task> { eggsTask, baconTask, toastTask };
while (breakfastTasks.Count > 0)
{
    Task finishedTask = await Task.WhenAny(breakfastTasks);
    if (finishedTask == eggsTask)
    {
        Console.WriteLine("eggs are ready");
    }
    else if (finishedTask == baconTask)
    {
        Console.WriteLine("bacon is ready");
    }
    else if (finishedTask == toastTask)
    {
        Console.WriteLine("toast is ready");
    }
    breakfastTasks.Remove(finishedTask);
}
```

<span data-ttu-id="ce45c-255">Después de todos estos cambios, la versión final del código tiene un aspecto similar al siguiente: <a id="final-version"></a>.</span><span class="sxs-lookup"><span data-stu-id="ce45c-255">After all those changes, the final version of the code looks like this: <a id="final-version"></a></span></span>
:::code language="csharp" source="snippets/index/AsyncBreakfast-final/Program.cs" highlight="9-40":::

:::image type="content" source="media/whenany-async-breakfast.png" alt-text="Cualquier desayuno asincrónico":::

<span data-ttu-id="ce45c-257">La versión final del desayuno preparado de forma asincrónica tardó aproximadamente 15 minutos porque algunas de las tareas se realizaron simultáneamente, y el código supervisó varias tareas a la vez y solo tuvo que actuar cuando fue necesario.</span><span class="sxs-lookup"><span data-stu-id="ce45c-257">The final version of the asynchronously prepared breakfast took roughly 15 minutes because some tasks ran concurrently, and the code monitored multiple tasks at once and only take action when it was needed.</span></span>

<span data-ttu-id="ce45c-258">Este código final es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ce45c-258">This final code is asynchronous.</span></span> <span data-ttu-id="ce45c-259">Refleja con más precisión la manera en que una persona prepara un desayuno.</span><span class="sxs-lookup"><span data-stu-id="ce45c-259">It more accurately reflects how a person would cook a breakfast.</span></span> <span data-ttu-id="ce45c-260">Compare el código anterior con el primer ejemplo de código del artículo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-260">Compare the preceding code with the first code sample in this article.</span></span> <span data-ttu-id="ce45c-261">Las acciones principales siguen siendo claras cuando se lee el código.</span><span class="sxs-lookup"><span data-stu-id="ce45c-261">The core actions are still clear from reading the code.</span></span> <span data-ttu-id="ce45c-262">De hecho, puede leerlo como si se tratara de las instrucciones para preparar el desayuno que se indican al principio del artículo.</span><span class="sxs-lookup"><span data-stu-id="ce45c-262">You can read this code the same way you'd read those instructions for making a breakfast at the beginning of this article.</span></span> <span data-ttu-id="ce45c-263">Las características del lenguaje para `async` y `await` proporcionan la traducción que cualquier persona haría para seguir las instrucciones escritas, a saber: las tareas deben iniciarse a medida que sea posible y debe evitarse el bloqueo por esperar a que se completen las tareas.</span><span class="sxs-lookup"><span data-stu-id="ce45c-263">The language features for `async` and `await` provide the translation every person makes to follow those written instructions: start tasks as you can and don't block waiting for tasks to complete.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce45c-264">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ce45c-264">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ce45c-265">Escenarios del mundo real para programas asincrónicos</span><span class="sxs-lookup"><span data-stu-id="ce45c-265">Explore real world scenarios for asynchronous programs</span></span>](../../../async.md)
