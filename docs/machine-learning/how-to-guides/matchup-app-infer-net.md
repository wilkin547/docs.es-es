---
title: 'Aplicación de enfrentamiento en juegos de Infer.NET: programación de probabilística'
description: Descubra cómo usar la programación probabilística con Infer.NET para crear una aplicación de listas de enfrentamientos en juegos basada en una versión simplificada de TrueSkill.
ms.date: 01/30/2020
ms.custom: mvc,how-to
ms.openlocfilehash: 8e489d61c5e6cca53ba12b13fddd0b73c7f85ef9
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092608"
---
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a><span data-ttu-id="3557e-103">Creación de una aplicación de listas de enfrentamientos en juegos con Infer.NET y programación probabilística</span><span class="sxs-lookup"><span data-stu-id="3557e-103">Create a game match up list app with Infer.NET and probabilistic programming</span></span>

<span data-ttu-id="3557e-104">Esta guía paso a paso le enseña la programación probabilística mediante Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="3557e-104">This how-to guide teaches you about probabilistic programming using Infer.NET.</span></span> <span data-ttu-id="3557e-105">La programación probabilística es un enfoque de aprendizaje automático donde los modelos personalizados se expresan como programas.</span><span class="sxs-lookup"><span data-stu-id="3557e-105">Probabilistic programming is a machine learning approach where custom models are expressed as computer programs.</span></span> <span data-ttu-id="3557e-106">Permite la incorporación del conocimiento del dominio en los modelos y hace que el sistema de aprendizaje automático sea más interpretable.</span><span class="sxs-lookup"><span data-stu-id="3557e-106">It allows for incorporating domain knowledge in the models and makes the machine learning system more interpretable.</span></span> <span data-ttu-id="3557e-107">También admite la inferencia en línea (proceso de aprendizaje a medida que llegan nuevos datos).</span><span class="sxs-lookup"><span data-stu-id="3557e-107">It also supports online inference – the process of learning as new data arrives.</span></span> <span data-ttu-id="3557e-108">Infer.NET se usa en varios productos de Microsoft, como Azure, Xbox y Bing.</span><span class="sxs-lookup"><span data-stu-id="3557e-108">Infer.NET is used in various products at Microsoft in Azure, Xbox, and Bing.</span></span>

## <a name="what-is-probabilistic-programming"></a><span data-ttu-id="3557e-109">¿Qué es la programación probabilística?</span><span class="sxs-lookup"><span data-stu-id="3557e-109">What is probabilistic programming?</span></span>

<span data-ttu-id="3557e-110">La programación probabilística permite crear modelos estadísticos de los procesos reales.</span><span class="sxs-lookup"><span data-stu-id="3557e-110">Probabilistic programming allows you to create statistical models of real-world processes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3557e-111">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3557e-111">Prerequisites</span></span>

- <span data-ttu-id="3557e-112">Configuración del entorno de desarrollo local</span><span class="sxs-lookup"><span data-stu-id="3557e-112">Local development environment setup</span></span>

  <span data-ttu-id="3557e-113">En esta guía paso a paso se supone que cuenta con una máquina que puede usar para el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="3557e-113">This how-to guide expects you to have a machine you can use for development.</span></span> <span data-ttu-id="3557e-114">El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en MacOS, Windows o Linux.</span><span class="sxs-lookup"><span data-stu-id="3557e-114">The .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) has instructions for setting up your local development environment on macOS, Windows, or Linux.</span></span>

## <a name="create-your-app"></a><span data-ttu-id="3557e-115">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="3557e-115">Create your app</span></span>

1. <span data-ttu-id="3557e-116">Abra un nuevo símbolo del sistema y ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="3557e-116">Open a new command prompt and run the following commands:</span></span>

```dotnetcli
dotnet new console -o myApp
cd myApp
```

<span data-ttu-id="3557e-117">El comando `dotnet` crea una aplicación `new` de tipo `console`.</span><span class="sxs-lookup"><span data-stu-id="3557e-117">The `dotnet` command creates a `new` application of type `console`.</span></span> <span data-ttu-id="3557e-118">El parámetro `-o` crea un directorio denominado `myApp` donde se almacena la aplicación y la rellena con los archivos necesarios.</span><span class="sxs-lookup"><span data-stu-id="3557e-118">The `-o` parameter creates a directory named `myApp` where your app is stored and populates it with the required files.</span></span> <span data-ttu-id="3557e-119">El comando `cd myApp` le coloca en el directorio de aplicación recién creada.</span><span class="sxs-lookup"><span data-stu-id="3557e-119">The `cd myApp` command puts you into the newly created app directory.</span></span>

## <a name="install-infernet-package"></a><span data-ttu-id="3557e-120">Instalación del paquete de Infer.NET</span><span class="sxs-lookup"><span data-stu-id="3557e-120">Install Infer.NET package</span></span>

<span data-ttu-id="3557e-121">Para usar Infer.NET, deberá instalar el paquete `Microsoft.ML.Probabilistic.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="3557e-121">To use Infer.NET, you need to install the `Microsoft.ML.Probabilistic.Compiler` package.</span></span> <span data-ttu-id="3557e-122">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3557e-122">In your command prompt, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a><span data-ttu-id="3557e-123">Diseño del modelo</span><span class="sxs-lookup"><span data-stu-id="3557e-123">Design your model</span></span>

<span data-ttu-id="3557e-124">En el ejemplo se usan las partidas de tenis de mesa o futbolín jugadas en la oficina.</span><span class="sxs-lookup"><span data-stu-id="3557e-124">The example sample uses table tennis or foosball matches played in the office.</span></span> <span data-ttu-id="3557e-125">Cuenta con los participantes y el resultado de cada partida.</span><span class="sxs-lookup"><span data-stu-id="3557e-125">You have the participants and outcome of each match.</span></span>  <span data-ttu-id="3557e-126">Quiere deducir las habilidades del jugador a partir de estos datos.</span><span class="sxs-lookup"><span data-stu-id="3557e-126">You want to infer the player's skills from this data.</span></span> <span data-ttu-id="3557e-127">Suponga que cada jugador tiene una habilidad latente normalmente distribuida y su rendimiento en una partida determinada es una versión con ruido de esta habilidad.</span><span class="sxs-lookup"><span data-stu-id="3557e-127">Assume that each player has a normally distributed latent skill and their given match performance is a noisy version of this skill.</span></span> <span data-ttu-id="3557e-128">Los datos limitan el rendimiento del ganador para que sea mayor que el rendimiento del perdedor.</span><span class="sxs-lookup"><span data-stu-id="3557e-128">The data constrains the winner’s performance to be greater than the loser’s performance.</span></span> <span data-ttu-id="3557e-129">Se trata de una versión simplificada del popular modelo de [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/), que también admite equipos, dibujos y otras extensiones.</span><span class="sxs-lookup"><span data-stu-id="3557e-129">This is a simplified version of the popular [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/) model, which also supports teams, draws, and other extensions.</span></span> <span data-ttu-id="3557e-130">Un [versión avanzada](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) de este modelo se utiliza para el emparejamiento en los títulos de juego más vendidos Halo y Gears of War.</span><span class="sxs-lookup"><span data-stu-id="3557e-130">An [advanced version](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) of this model is used for matchmaking in the best-selling game titles Halo and Gears of War.</span></span>

<span data-ttu-id="3557e-131">Necesita enumerar las habilidades del jugador deducidas, junto con su desviación (la medida de incertidumbre en torno a las habilidades).</span><span class="sxs-lookup"><span data-stu-id="3557e-131">You need to list the inferred player skills, alongside with their variance – the measure of uncertainty around the skills.</span></span>

<span data-ttu-id="3557e-132">*Datos de ejemplo del resultado de las partidas*</span><span class="sxs-lookup"><span data-stu-id="3557e-132">*Game result sample data*</span></span>

<span data-ttu-id="3557e-133">Juego</span><span class="sxs-lookup"><span data-stu-id="3557e-133">Game</span></span> |<span data-ttu-id="3557e-134">Ganador</span><span class="sxs-lookup"><span data-stu-id="3557e-134">Winner</span></span> | <span data-ttu-id="3557e-135">Perdedor</span><span class="sxs-lookup"><span data-stu-id="3557e-135">Loser</span></span>
---------|----------|---------
 <span data-ttu-id="3557e-136">1</span><span class="sxs-lookup"><span data-stu-id="3557e-136">1</span></span> | <span data-ttu-id="3557e-137">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="3557e-137">Player 0</span></span> | <span data-ttu-id="3557e-138">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="3557e-138">Player 1</span></span>
 <span data-ttu-id="3557e-139">2</span><span class="sxs-lookup"><span data-stu-id="3557e-139">2</span></span> | <span data-ttu-id="3557e-140">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="3557e-140">Player 0</span></span> | <span data-ttu-id="3557e-141">Jugador 3</span><span class="sxs-lookup"><span data-stu-id="3557e-141">Player 3</span></span>
 <span data-ttu-id="3557e-142">3</span><span class="sxs-lookup"><span data-stu-id="3557e-142">3</span></span> | <span data-ttu-id="3557e-143">Jugador 0</span><span class="sxs-lookup"><span data-stu-id="3557e-143">Player 0</span></span> | <span data-ttu-id="3557e-144">Jugador 4</span><span class="sxs-lookup"><span data-stu-id="3557e-144">Player 4</span></span>
 <span data-ttu-id="3557e-145">4</span><span class="sxs-lookup"><span data-stu-id="3557e-145">4</span></span> | <span data-ttu-id="3557e-146">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="3557e-146">Player 1</span></span> | <span data-ttu-id="3557e-147">Jugador 2</span><span class="sxs-lookup"><span data-stu-id="3557e-147">Player 2</span></span>
 <span data-ttu-id="3557e-148">5</span><span class="sxs-lookup"><span data-stu-id="3557e-148">5</span></span> | <span data-ttu-id="3557e-149">Jugador 3</span><span class="sxs-lookup"><span data-stu-id="3557e-149">Player 3</span></span> | <span data-ttu-id="3557e-150">Jugador 1</span><span class="sxs-lookup"><span data-stu-id="3557e-150">Player 1</span></span>
 <span data-ttu-id="3557e-151">6</span><span class="sxs-lookup"><span data-stu-id="3557e-151">6</span></span> | <span data-ttu-id="3557e-152">Jugador 4</span><span class="sxs-lookup"><span data-stu-id="3557e-152">Player 4</span></span> | <span data-ttu-id="3557e-153">Jugador 2</span><span class="sxs-lookup"><span data-stu-id="3557e-153">Player 2</span></span>

<span data-ttu-id="3557e-154">Examinando más detalladamente los datos de ejemplo, observará que los jugadores 3 y 4 tienen una victoria y una derrota.</span><span class="sxs-lookup"><span data-stu-id="3557e-154">With a closer look at the sample data, you’ll notice that players 3 and 4 both have one win and one loss.</span></span> <span data-ttu-id="3557e-155">Veamos las clasificaciones mediante programación probabilística.</span><span class="sxs-lookup"><span data-stu-id="3557e-155">Let's see what the rankings look like using probabilistic programming.</span></span> <span data-ttu-id="3557e-156">Observe que también hay un jugador cero porque incluso las listas de enfrentamientos de la oficina son cero según nuestros desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="3557e-156">Notice also there is a player zero because even office match up lists are zero based to us developers.</span></span>

## <a name="write-some-code"></a><span data-ttu-id="3557e-157">Escritura de algo de código</span><span class="sxs-lookup"><span data-stu-id="3557e-157">Write some code</span></span>

<span data-ttu-id="3557e-158">Una vez diseñado el modelo, es el momento de expresarlo como un programa probabilístico mediante la API de modelado de Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="3557e-158">Having designed the model, it’s time to express it as a probabilistic program using the Infer.NET modeling API.</span></span> <span data-ttu-id="3557e-159">Abra `Program.cs` en el editor de texto que prefiera y reemplace todo su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3557e-159">Open `Program.cs` in your favorite text editor and replace all of its contents with the following code:</span></span>

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

## <a name="run-your-app"></a><span data-ttu-id="3557e-160">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="3557e-160">Run your app</span></span>

<span data-ttu-id="3557e-161">En el símbolo del sistema, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3557e-161">In your command prompt, run the following command:</span></span>

```dotnetcli
dotnet run
```

## <a name="results"></a><span data-ttu-id="3557e-162">Resultados</span><span class="sxs-lookup"><span data-stu-id="3557e-162">Results</span></span>

<span data-ttu-id="3557e-163">Los resultados deberían ser similares a los indicados a continuación:</span><span class="sxs-lookup"><span data-stu-id="3557e-163">Your results should be similar to the following:</span></span>

```console
Compiling model...done.
Iterating:
.........|.........|.........|.........|.........| 50
Player 0 skill: Gaussian(9.517, 3.926)
Player 3 skill: Gaussian(6.834, 3.892)
Player 4 skill: Gaussian(6.054, 4.731)
Player 1 skill: Gaussian(4.955, 3.503)
Player 2 skill: Gaussian(2.639, 4.288)
```

<span data-ttu-id="3557e-164">En los resultados, observe que el jugador 3 está clasificado ligeramente por encima del jugador 4 según nuestro modelo.</span><span class="sxs-lookup"><span data-stu-id="3557e-164">In the results, notice that player 3 ranks slightly higher than player 4 according to our model.</span></span> <span data-ttu-id="3557e-165">Eso es porque la victoria del jugador 3 sobre el jugador 1 es más importante que la victoria del jugador 4 sobre el jugador 2 (tenga en cuenta que el jugador 1 venció al jugador 2).</span><span class="sxs-lookup"><span data-stu-id="3557e-165">That’s because the victory of player 3 over player 1 is more significant than the victory of player 4 over player 2 – note that player 1 beats player 2.</span></span> <span data-ttu-id="3557e-166">¡El jugador 0 es el campeón general!</span><span class="sxs-lookup"><span data-stu-id="3557e-166">Player 0 is the overall champ!</span></span>

## <a name="keep-learning"></a><span data-ttu-id="3557e-167">Mantenimiento del aprendizaje</span><span class="sxs-lookup"><span data-stu-id="3557e-167">Keep learning</span></span>

<span data-ttu-id="3557e-168">El diseño de modelos estadísticos es una habilidad por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="3557e-168">Designing statistical models is a skill on its own.</span></span> <span data-ttu-id="3557e-169">El equipo de Microsoft Research Cambridge ha escrito un [libro en línea gratuito](http://mbmlbook.com/), que ofrece una breve introducción al artículo.</span><span class="sxs-lookup"><span data-stu-id="3557e-169">The Microsoft Research Cambridge team has written a [free online book](http://mbmlbook.com/), which gives a gentle introduction to the article.</span></span> <span data-ttu-id="3557e-170">El capítulo 3 de este libro trata sobre el modelo TrueSkill con más detalle.</span><span class="sxs-lookup"><span data-stu-id="3557e-170">Chapter 3 of this book covers the TrueSkill model in more detail.</span></span> <span data-ttu-id="3557e-171">Cuando tenga un modelo en mente, puede transformarlo en código mediante la [amplia documentación](https://dotnet.github.io/infer/) existente en el sitio web de Infer.NET.</span><span class="sxs-lookup"><span data-stu-id="3557e-171">Once you have a model in mind, you can transform it into code using the [extensive documentation](https://dotnet.github.io/infer/) on the Infer.NET website.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3557e-172">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3557e-172">Next steps</span></span>

<span data-ttu-id="3557e-173">Visite el repositorio de GitHub de Infer.NET para seguir aprendiendo y encontrar más ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3557e-173">Check out the Infer.NET GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3557e-174">Repositorio de GitHub de dotnet e infer</span><span class="sxs-lookup"><span data-stu-id="3557e-174">dotnet/infer GitHub repository</span></span>](https://github.com/dotnet/infer)
