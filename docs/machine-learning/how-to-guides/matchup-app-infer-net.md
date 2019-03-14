---
title: Creación de una aplicación de listas de enfrentamientos en juegos con Infer.NET y programación probabilística
description: Descubra cómo usar la programación probabilística con Infer.NET para crear una aplicación de listas de enfrentamientos en juegos basada en una versión simplificada de TrueSkill.
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 06538ec9de26f5aeabe474fbcae69f0a313c8d32
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679143"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="f84e5-103">Creación de una aplicación de listas de enfrentamientos en juegos con Infer.NET y programación probabilística</span><span class="sxs-lookup"><span data-stu-id="f84e5-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

> [!NOTE]
> <span data-ttu-id="f84e5-104">Este tema hace referencia a ML.NET, que se encuentra actualmente en versión preliminar, por lo que el material está sujeto a cambios.</span><span class="sxs-lookup"><span data-stu-id="f84e5-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="f84e5-105">Para obtener más información, visite [la introducción de ML.NET](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span><span class="sxs-lookup"><span data-stu-id="f84e5-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="f84e5-106">Este tutorial y el ejemplo relacionado usan actualmente **ML.NET en su versión 0.10**.</span><span class="sxs-lookup"><span data-stu-id="f84e5-106">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="f84e5-107">Para obtener más información, consulte las notas de la versión en el [repositorio de GitHub dotnet/machinelearning](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span><span class="sxs-lookup"><span data-stu-id="f84e5-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="f84e5-108">Esta guía paso a paso le enseña la programación probabilística mediante Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="f84e5-108">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="f84e5-109">La programación probabilística es un enfoque de aprendizaje automático donde los modelos personalizados se expresan como programas.</span><span class="sxs-lookup"><span data-stu-id="f84e5-109">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="f84e5-110">Permite la incorporación del conocimiento del dominio en los modelos y hace que el sistema de aprendizaje automático sea más interpretable.</span><span class="sxs-lookup"><span data-stu-id="f84e5-110">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="f84e5-111">También admite la inferencia en línea (proceso de aprendizaje a medida que llegan nuevos datos).</span><span class="sxs-lookup"><span data-stu-id="f84e5-111">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="f84e5-112">Infer.NET se usa en varios productos de Microsoft, como Azure, Xbox y Bing.</span><span class="sxs-lookup"><span data-stu-id="f84e5-112">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="f84e5-113">¿Qué es la programación probabilística?</span><span class="sxs-lookup"><span data-stu-id="f84e5-113">What is probabilistic programming?</span></span>

<span data-ttu-id="f84e5-114">La programación probabilística permite crear modelos estadísticos de los procesos reales.</span><span class="sxs-lookup"><span data-stu-id="f84e5-114">Probabilistic programming allows you to create statistical models of real-world processes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f84e5-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f84e5-115">Prerequisites</span></span>

- <span data-ttu-id="f84e5-116">Configuración del entorno de desarrollo local</span><span class="sxs-lookup"><span data-stu-id="f84e5-116">Local development environment setup</span></span>

  <span data-ttu-id="f84e5-117">En esta guía paso a paso se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f84e5-117">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="f84e5-118">El tutorial [Iniciar en 10 minutos](https://www.microsoft.com/net/core) de .NET cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.</span><span class="sxs-lookup"><span data-stu-id="f84e5-118">The .NET [Get Started in 10 minutes](https://www.microsoft.com/net/core) tutorial has instructions for setting up your local development environment on Mac, PC, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="f84e5-119">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f84e5-119">Create your app</span></span>

1. <span data-ttu-id="f84e5-120">Abra un nuevo símbolo del sistema y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="f84e5-120">Open a new command prompt and run the following commands:</span></span>

```console
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="f84e5-121">El comando `dotnet` crea una aplicación `new` de tipo `console`.</span><span class="sxs-lookup"><span data-stu-id="f84e5-121">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="f84e5-122">El parámetro `-o` crea un directorio denominado `myApp` donde se almacena la aplicación y la rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="f84e5-122">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="f84e5-123">El comando `cd myApp` le coloca en el directorio de aplicación recién creada.</span><span class="sxs-lookup"><span data-stu-id="f84e5-123">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="f84e5-124">Instalación del paquete de Infer.NET</span><span class="sxs-lookup"><span data-stu-id="f84e5-124">Install Infer.NET package</span></span>

<span data-ttu-id="f84e5-125">Para usar Infer.NET, deberá instalar el paquete `Microsoft.ML.Probabilistic.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="f84e5-125">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="f84e5-126">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f84e5-126">In your command prompt, run the following command:</span></span>

```console
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="f84e5-127">Diseño del modelo</span><span class="sxs-lookup"><span data-stu-id="f84e5-127">Design your model</span></span>

<span data-ttu-id="f84e5-128">En el ejemplo se usan las partidas de tenis de mesa o futbolín jugadas en la oficina.</span><span class="sxs-lookup"><span data-stu-id="f84e5-128">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="f84e5-129">Cuenta con los participantes y el resultado de cada partida.</span><span class="sxs-lookup"><span data-stu-id="f84e5-129">You have the participants and outcome of each match.</span></span>  <span data-ttu-id="f84e5-130">Quiere deducir las habilidades del jugador a partir de estos datos.</span><span class="sxs-lookup"><span data-stu-id="f84e5-130">You want to infer the player's skills from this data.</span></span> <span data-ttu-id="f84e5-131">Suponga que cada jugador tiene una habilidad latente normalmente distribuida y su rendimiento en una partida determinada es una versión con ruido de esta habilidad.</span><span class="sxs-lookup"><span data-stu-id="f84e5-131">Assume that each player has a normally distributed latent skill and their given match performance is a noisy version of this skill.</span></span> <span data-ttu-id="f84e5-132">Los datos limitan el rendimiento del ganador para que sea mayor que el rendimiento del perdedor.</span><span class="sxs-lookup"><span data-stu-id="f84e5-132">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="f84e5-133">Se trata de una versión simplificada del popular modelo de [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/), que también admite equipos, dibujos y otras extensiones.</span><span class="sxs-lookup"><span data-stu-id="f84e5-133">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/en-us/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="f84e5-134">Un [versión avanzada](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) de este modelo se utiliza para el emparejamiento en los títulos de juego más vendidos Halo y Gears of War.</span><span class="sxs-lookup"><span data-stu-id="f84e5-134">An [advanced version](https://www.microsoft.com/en-us/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="f84e5-135">Necesita enumerar las habilidades del jugador deducidas, junto con su desviación (la medida de incertidumbre en torno a las habilidades).</span><span class="sxs-lookup"><span data-stu-id="f84e5-135">You need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="f84e5-136">*Datos de ejemplo del resultado de las partidas*</span><span class="sxs-lookup"><span data-stu-id="f84e5-136">*Game result sample data*</span></span>

<span data-ttu-id="f84e5-137">Juego</span><span class="sxs-lookup"><span data-stu-id="f84e5-137">Game</span></span> |<span data-ttu-id="f84e5-138">Ganador</span><span class="sxs-lookup"><span data-stu-id="f84e5-138">Winner</span></span> | <span data-ttu-id="f84e5-139">Perdedor</span><span class="sxs-lookup"><span data-stu-id="f84e5-139">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="f84e5-140">1</span><span class="sxs-lookup"><span data-stu-id="f84e5-140">1</span></span> | <span data-ttu-id="f84e5-141">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="f84e5-141">Player 0</span></span> | <span data-ttu-id="f84e5-142">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="f84e5-142">Player 1</span></span>
 <span data-ttu-id="f84e5-143">2</span><span class="sxs-lookup"><span data-stu-id="f84e5-143">2</span></span> | <span data-ttu-id="f84e5-144">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="f84e5-144">Player 0</span></span> | <span data-ttu-id="f84e5-145">Jugador 3</span><span class="sxs-lookup"><span data-stu-id="f84e5-145">Player 3</span></span>
 <span data-ttu-id="f84e5-146">3</span><span class="sxs-lookup"><span data-stu-id="f84e5-146">3</span></span> | <span data-ttu-id="f84e5-147">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="f84e5-147">Player 0</span></span> | <span data-ttu-id="f84e5-148">Jugador 4</span><span class="sxs-lookup"><span data-stu-id="f84e5-148">Player 4</span></span>
 <span data-ttu-id="f84e5-149">4</span><span class="sxs-lookup"><span data-stu-id="f84e5-149">4</span></span> | <span data-ttu-id="f84e5-150">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="f84e5-150">Player 1</span></span> | <span data-ttu-id="f84e5-151">Jugador 2</span><span class="sxs-lookup"><span data-stu-id="f84e5-151">Player 2</span></span>
 <span data-ttu-id="f84e5-152">5</span><span class="sxs-lookup"><span data-stu-id="f84e5-152">5</span></span> | <span data-ttu-id="f84e5-153">Jugador 3</span><span class="sxs-lookup"><span data-stu-id="f84e5-153">Player 3</span></span> | <span data-ttu-id="f84e5-154">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="f84e5-154">Player 1</span></span>
 <span data-ttu-id="f84e5-155">6</span><span class="sxs-lookup"><span data-stu-id="f84e5-155">6</span></span> | <span data-ttu-id="f84e5-156">Jugador 4</span><span class="sxs-lookup"><span data-stu-id="f84e5-156">Player 4</span></span> | <span data-ttu-id="f84e5-157">Jugador 2</span><span class="sxs-lookup"><span data-stu-id="f84e5-157">Player 2</span></span>

<span data-ttu-id="f84e5-158">Examinando más detalladamente los datos de ejemplo, observará que los jugadores 3 y 4 tienen una victoria y una derrota.</span><span class="sxs-lookup"><span data-stu-id="f84e5-158">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="f84e5-159">Veamos las clasificaciones mediante programación probabilística.</span><span class="sxs-lookup"><span data-stu-id="f84e5-159">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="f84e5-160">Observe que también hay un jugador cero porque incluso las listas de enfrentamientos de la oficina son cero según nuestros desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="f84e5-160">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="f84e5-161">Escritura de algo de código</span><span class="sxs-lookup"><span data-stu-id="f84e5-161">Write some code</span></span>

<span data-ttu-id="f84e5-162">Una vez diseñado el modelo, es el momento de expresarlo como un programa probabilístico mediante la API de modelado de Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="f84e5-162">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="f84e5-163">Abra `Program.cs` en el editor de texto que prefiera y reemplace todo su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f84e5-163">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

```csharp
namespace myApp

{
    using System;
    using System.Linq;
    using Microsoft.ML.Probabilistic;
    using Microsoft.ML.Probabilistic.Distributions;
    using Microsoft.ML.Probabilistic.Models;

    class Program
    {

        static void Main(string[] args)
        {
            // The winner and loser in each of 6 samples games
            var winnerData = new[] { 0, 0, 0, 1, 3, 4 };
            var loserData = new[] { 1, 3, 4, 2, 1, 2 };

            // Define the statistical model as a probabilistic program
            var game = new Range(winnerData.Length);
            var player = new Range(winnerData.Concat(loserData).Max() + 1);
            var playerSkills = Variable.Array<double>(player);
            playerSkills[player] = Variable.GaussianFromMeanAndVariance(6, 9).ForEach(player);

            var winners = Variable.Array<int>(game);
            var losers = Variable.Array<int>(game);

            using (Variable.ForEach(game))
            {
                // The player performance is a noisy version of their skill
                var winnerPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[winners[game]], 1.0);
                var loserPerformance = Variable.GaussianFromMeanAndVariance(playerSkills[losers[game]], 1.0);

                // The winner performed better in this game
                Variable.ConstrainTrue(winnerPerformance > loserPerformance);
            }

            // Attach the data to the model
            winners.ObservedValue = winnerData;
            losers.ObservedValue = loserData;

            // Run inference
            var inferenceEngine = new InferenceEngine();
            var inferredSkills = inferenceEngine.Infer<Gaussian[]>(playerSkills);

            // The inferred skills are uncertain, which is captured in their variance
            var orderedPlayerSkills = inferredSkills
               .Select((s, i) => new { Player = i, Skill = s })
               .OrderByDescending(ps => ps.Skill.GetMean());

            foreach (var playerSkill in orderedPlayerSkills)
            {
                Console.WriteLine($"Player {playerSkill.Player} skill: {playerSkill.Skill}");
            }
        }
    }
}
```

## <a name="run-your-app"></a><span data-ttu-id="f84e5-164">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f84e5-164">Run your app</span></span>

<span data-ttu-id="f84e5-165">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f84e5-165">In your command prompt, run the following command:</span></span>

```console
dotnet run
```

## <a name="results"></a><span data-ttu-id="f84e5-166">Resultados</span><span class="sxs-lookup"><span data-stu-id="f84e5-166">Results</span></span>

<span data-ttu-id="f84e5-167">Los resultados deberían ser similares a los indicados a continuación:</span><span class="sxs-lookup"><span data-stu-id="f84e5-167">Your results should be similar to the following:</span></span>

```
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="f84e5-168">En los resultados, observe que el jugador 3 está clasificado ligeramente por encima del jugador 4 según nuestro modelo.</span><span class="sxs-lookup"><span data-stu-id="f84e5-168">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="f84e5-169">Eso es porque la victoria del jugador 3 sobre el jugador 1 es más importante que la victoria del jugador 4 sobre el jugador 2 (tenga en cuenta que el jugador 1 venció al jugador 2).</span><span class="sxs-lookup"><span data-stu-id="f84e5-169">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="f84e5-170">¡El jugador 0 es el campeón general!</span><span class="sxs-lookup"><span data-stu-id="f84e5-170">Player 0 is the overall champ!</span></span>

## <a name="keep-learning"></a><span data-ttu-id="f84e5-171">Mantenimiento del aprendizaje</span><span class="sxs-lookup"><span data-stu-id="f84e5-171">Keep learning</span></span>

<span data-ttu-id="f84e5-172">El diseño de modelos estadísticos es una habilidad por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f84e5-172">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="f84e5-173">El equipo de Microsoft Research Cambridge ha escrito un [libro en línea gratuito](http://mbmlbook.com/), que ofrece una breve introducción al artículo.</span><span class="sxs-lookup"><span data-stu-id="f84e5-173">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="f84e5-174">El capítulo 3 de este libro trata sobre el modelo TrueSkill con más detalle.</span><span class="sxs-lookup"><span data-stu-id="f84e5-174">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="f84e5-175">Cuando tenga un modelo en mente, puede transformarlo en código mediante la [amplia documentación](https://dotnet.github.io/infer/) existente en el sitio web de Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="f84e5-175">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f84e5-176">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f84e5-176">Next steps</span></span>

<span data-ttu-id="f84e5-177">Visite el repositorio de GitHub de Infer.NET para seguir aprendiendo y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f84e5-177">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f84e5-178">Repositorio de GitHub de dotnet e infer</span><span class="sxs-lookup"><span data-stu-id="f84e5-178">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)
