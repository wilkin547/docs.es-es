---
title: "Introducción a .NET Core en Windows con Visual Studio 2017"
description: "Introducción a .NET Core en Windows con Visual Studio 2017"
keywords: .NET, .NET Core
author: bleroy
manager: wpickett
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d743134a-08a3-4ff6-aab7-49f71f0568c3
translationtype: Human Translation
ms.sourcegitcommit: 71eab6216e116b99927dfeaa8ce3cf70bcc08a5e
ms.openlocfilehash: 4437f44523bcc4e8517de5b6be42a63439f817d7

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017"></a>Introducción a .NET Core en Windows con Visual Studio 2017

por [Bertrand Le Roy](https://github.com/bleroy) y [Phillip Carter](https://github.com/cartermp)

Visual Studio 2017 proporciona un entorno de desarrollo completo para las aplicaciones .NET Core. Los procedimientos de este documento describen los pasos necesarios para crear una aplicación de consola muy simple mediante Visual Studio y .NET Core.

## <a name="prerequisites"></a>Requisitos previos

Siga las instrucciones de [nuestra página de requisitos previos](../windows-prerequisites.md) para actualizar su entorno.

## <a name="getting-started"></a>Introducción

En los pasos siguientes se configurará Visual Studio 2017 para el desarrollo de aplicaciones de consola de .NET Core:

1. Abra Visual Studio y, en el menú **Archivo**, elija **Nuevo**, **Proyecto**.

2. En el cuadro de diálogo **Nuevo proyecto**, en la lista **Plantillas**, expanda el nodo **Visual C#** y elija **.NET Core**. debe ver cuatro nuevas plantillas para **Aplicación de consola (.NET Core)**, **Proyecto de prueba unitaria (.NET Core)**, **Biblioteca de clases (.NET Core)**, and **Aplicación web de ASP.NET Core (.NET Core)**. Elija **Aplicación de consola (.NET Core)**, escriba un nombre para el proyecto, elija una ubicación y luego haga clic en Aceptar.

  ![Nuevo proyecto: aplicación de consola](media/new-project-console-app.png)

3. El proyecto resultante tiene un único archivo de C# que enviará "Hola a todos" a la consola.

  ![El proyecto de aplicación de consola](media/console-app-solution.png)

Puede ejecutar esta aplicación en modo de depuración presionando F5, o en modo de lanzamiento con CTRL + F5. También puede establecer puntos de interrupción para interrumpir la ejecución e inspeccionar variables, o empezar a escribir código más interesante.

¡Que disfrute programando!

## <a name="what-to-do-next"></a>Pasos siguientes

Después de esta sencilla introducción, probablemente se esté preguntando cómo crear soluciones más avanzadas, con bibliotecas y pruebas reutilizables. En el tema [Creación de una solución completa de .NET Core en Windows con Visual Studio 2017](using-on-windows-vs-2017-full-solution.md) se muestra cómo hacer eso.



<!--HONumber=Nov16_HO3-->


