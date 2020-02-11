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
# <a name="create-a-game-match-up-list-app-with-infernet-and-probabilistic-programming"></a>Creación de una aplicación de listas de enfrentamientos en juegos con Infer.NET y programación probabilística

Esta guía paso a paso le enseña la programación probabilística mediante Infer.NET. La programación probabilística es un enfoque de aprendizaje automático donde los modelos personalizados se expresan como programas. Permite la incorporación del conocimiento del dominio en los modelos y hace que el sistema de aprendizaje automático sea más interpretable. También admite la inferencia en línea (proceso de aprendizaje a medida que llegan nuevos datos). Infer.NET se usa en varios productos de Microsoft, como Azure, Xbox y Bing.

## <a name="what-is-probabilistic-programming"></a>¿Qué es la programación probabilística?

La programación probabilística permite crear modelos estadísticos de los procesos reales.

## <a name="prerequisites"></a>Requisitos previos

- Configuración del entorno de desarrollo local

  En esta guía paso a paso se supone que cuenta con una máquina que puede usar para el desarrollo. El tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro) cuenta con instrucciones para configurar el entorno de desarrollo local en MacOS, Windows o Linux.

## <a name="create-your-app"></a>Creación de una aplicación

1. Abra un nuevo símbolo del sistema y ejecute los siguientes comandos:

```dotnetcli
dotnet new console -o myApp
cd myApp
```

El comando `dotnet` crea una aplicación `new` de tipo `console`. El parámetro `-o` crea un directorio denominado `myApp` donde se almacena la aplicación y la rellena con los archivos necesarios. El comando `cd myApp` le coloca en el directorio de aplicación recién creada.

## <a name="install-infernet-package"></a>Instalación del paquete de Infer.NET

Para usar Infer.NET, deberá instalar el paquete `Microsoft.ML.Probabilistic.Compiler`. En el símbolo del sistema, ejecute el siguiente comando:

```dotnetcli
dotnet add package Microsoft.ML.Probabilistic.Compiler
```

## <a name="design-your-model"></a>Diseño del modelo

En el ejemplo se usan las partidas de tenis de mesa o futbolín jugadas en la oficina. Cuenta con los participantes y el resultado de cada partida.  Quiere deducir las habilidades del jugador a partir de estos datos. Suponga que cada jugador tiene una habilidad latente normalmente distribuida y su rendimiento en una partida determinada es una versión con ruido de esta habilidad. Los datos limitan el rendimiento del ganador para que sea mayor que el rendimiento del perdedor. Se trata de una versión simplificada del popular modelo de [TrueSkill](https://www.microsoft.com/research/project/trueskill-ranking-system/), que también admite equipos, dibujos y otras extensiones. Un [versión avanzada](https://www.microsoft.com/research/publication/trueskill-2-improved-bayesian-skill-rating-system/) de este modelo se utiliza para el emparejamiento en los títulos de juego más vendidos Halo y Gears of War.

Necesita enumerar las habilidades del jugador deducidas, junto con su desviación (la medida de incertidumbre en torno a las habilidades).

*Datos de ejemplo del resultado de las partidas*

Juego |Ganador | Perdedor
---------|----------|---------
 1 | Jugador 0 | Jugador 1
 2 | Jugador 0 | Jugador 3
 3 | Jugador 0 | Jugador 4
 4 | Jugador 1 | Jugador 2
 5 | Jugador 3 | Jugador 1
 6 | Jugador 4 | Jugador 2

Examinando más detalladamente los datos de ejemplo, observará que los jugadores 3 y 4 tienen una victoria y una derrota. Veamos las clasificaciones mediante programación probabilística. Observe que también hay un jugador cero porque incluso las listas de enfrentamientos de la oficina son cero según nuestros desarrolladores.

## <a name="write-some-code"></a>Escritura de algo de código

Una vez diseñado el modelo, es el momento de expresarlo como un programa probabilístico mediante la API de modelado de Infer.NET. Abra `Program.cs` en el editor de texto que prefiera y reemplace todo su contenido por el código siguiente:

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

## <a name="run-your-app"></a>Ejecutar la aplicación

En el símbolo del sistema, ejecute el siguiente comando:

```dotnetcli
dotnet run
```

## <a name="results"></a>Resultados

Los resultados deberían ser similares a los indicados a continuación:

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

En los resultados, observe que el jugador 3 está clasificado ligeramente por encima del jugador 4 según nuestro modelo. Eso es porque la victoria del jugador 3 sobre el jugador 1 es más importante que la victoria del jugador 4 sobre el jugador 2 (tenga en cuenta que el jugador 1 venció al jugador 2). ¡El jugador 0 es el campeón general!

## <a name="keep-learning"></a>Mantenimiento del aprendizaje

El diseño de modelos estadísticos es una habilidad por sí mismo. El equipo de Microsoft Research Cambridge ha escrito un [libro en línea gratuito](http://mbmlbook.com/), que ofrece una breve introducción al artículo. El capítulo 3 de este libro trata sobre el modelo TrueSkill con más detalle. Cuando tenga un modelo en mente, puede transformarlo en código mediante la [amplia documentación](https://dotnet.github.io/infer/) existente en el sitio web de Infer.NET.

## <a name="next-steps"></a>Pasos siguientes

Visite el repositorio de GitHub de Infer.NET para seguir aprendiendo y encontrar más ejemplos.
> [!div class="nextstepaction"]
> [Repositorio de GitHub de dotnet e infer](https://github.com/dotnet/infer)
