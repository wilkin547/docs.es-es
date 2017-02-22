---
title: "Introducción a .NET Core en Windows con Visual Studio 2017 | Microsoft Docs"
description: "Introducción a .NET Core en Windows con Visual Studio 2017"
keywords: .NET, .NET Core
author: bleroy
ms.author: mairaw
ms.date: 01/18/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 613c65d0-f773-41b8-ba0e-83f6a82a0b30
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: cc2c2853bc31e161d1fe0de4edc71d15281c6d24

---

# <a name="getting-started-with-net-core-on-windows-using-visual-studio-2017-net-core-tools-rc4"></a>Introducción a .NET Core en Windows con Visual Studio 2017 (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2 de Visual Studio 2015, consulte el tema [Introducción a .NET Core en Windows con Visual Studio 2015](../../tutorials/using-on-windows.md).

Visual Studio 2017 proporciona un entorno de desarrollo completo para las aplicaciones .NET Core. Los procedimientos de este documento describen los pasos necesarios para crear una aplicación de consola muy simple mediante Visual Studio y .NET Core.

## <a name="prerequisites"></a>Requisitos previos

Siga las instrucciones de [nuestra página de requisitos previos](../windows-prerequisites.md) para actualizar su entorno.

## <a name="getting-started"></a>Introducción

En los pasos siguientes se configurará Visual Studio 2017 para el desarrollo de aplicaciones de consola de .NET Core:

1. Abra Visual Studio y, en el menú **Archivo**, elija **Nuevo**, **Proyecto**.

2. En el cuadro de diálogo **Nuevo proyecto**, en la lista **Plantillas**, expanda el nodo **Visual C#** y elija **.NET Core**. Debe ver cinco plantillas de proyecto para **Aplicación de consola (.NET Core)**, **Biblioteca de clases (.NET Standard)**, **Proyecto de prueba unitaria (.NET Core)**, **Biblioteca de clases (.NET Core)** y **Aplicación web ASP.NET Core (.NET Core)**. Elija **Aplicación de consola (.NET Core)**, escriba un nombre para el proyecto, elija una ubicación y luego haga clic en Aceptar.

  ![Nuevo proyecto: aplicación de consola](media/new-project-console-app.png)

3. El proyecto resultante tiene un único archivo de C# que enviará "Hola a todos" a la consola.

  ![El proyecto de aplicación de consola](media/console-app-solution.png)

Puede ejecutar esta aplicación en modo de depuración presionando F5, o en modo de lanzamiento con CTRL + F5. También puede establecer puntos de interrupción para interrumpir la ejecución e inspeccionar variables, o empezar a escribir código más interesante.

¡Que disfrute programando!

## <a name="next-steps"></a>Pasos siguientes

Después de esta sencilla introducción, probablemente se esté preguntando cómo crear soluciones más avanzadas, con bibliotecas y pruebas reutilizables. En el tema [Creación de una solución completa de .NET Core en Windows con Visual Studio 2017](using-on-windows-vs-2017-full-solution.md) se muestra cómo hacer eso.



<!--HONumber=Feb17_HO2-->


