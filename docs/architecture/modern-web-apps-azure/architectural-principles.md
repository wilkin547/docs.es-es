---
title: Principios de la arquitectura
description: Diseño de aplicaciones web modernas con ASP.NET Core y Azure | Principios de la arquitectura
author: ardalis
ms.author: wiwagn
ms.date: 12/04/2019
ms.openlocfilehash: e291888bee25a9c87259560ca4b12635ee73c3c7
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975412"
---
# <a name="architectural-principles"></a>Principios de la arquitectura

> "Si los constructores construyeran los edificios como los programadores escriben los programas, el primer pájaro carpintero que apareciera destruiría la civilización".  
> _\- Gerald Weinberg_

Las soluciones de software se deben diseñar y crear con el mantenimiento en mente. Los principios que se describen en esta sección le ayudarán a tomar decisiones arquitectónicas que darán como resultado aplicaciones limpias y fácil de mantener. Por lo general, estos principios le ayudarán a compilar aplicaciones a partir de componentes discretos que no están estrechamente relacionados con otras partes de la aplicación, sino que se comunican a través de interfaces explícitas o sistemas de mensajería.

## <a name="common-design-principles"></a>Principios de diseño comunes

### <a name="separation-of-concerns"></a>Separación de intereses

Un principio fundamental durante el desarrollo es la **separación de intereses**. Este principio afirma que el software se debe separar en función de los tipos de trabajo que realiza. Por ejemplo, considere una aplicación que incluye lógica para identificar los elementos de interés que se van a mostrar al usuario y que da formato a estos elementos de una manera determinada para hacerlos más evidentes. El comportamiento responsable de elegir a qué elementos dar formato se debe mantener separado del comportamiento responsable de dar formato a los elementos, puesto que estos son intereses independientes que solo se relacionan entre sí de manera casual.

Arquitectónicamente, las aplicaciones se pueden crear de forma lógica para seguir este principio mediante la separación del comportamiento de negocios principal de la lógica de la interfaz de usuario y la infraestructura. Idealmente, la lógica y las reglas de negocios deben residir en un proyecto independiente, que no debería depender de otros proyectos de la aplicación. Esto ayuda a garantizar que el modelo de negocio sea fácil de probar y pueda evolucionar sin que se esté estrechamente unido a detalles de implementación de bajo nivel. La separación de intereses es una consideración clave detrás del uso de capas en arquitecturas de aplicación.

### <a name="encapsulation"></a>Encapsulación

Las diferentes partes de una aplicación deben usar la **encapsulación** para aislarse de otras partes de la aplicación. Las capas y los componentes de la aplicación deben poder ajustar su implementación interna sin interrumpir a sus colaboradores mientras no se infrinjan los externos. El uso correcto de la encapsulación contribuye a lograr el acoplamiento flexible y la modularidad en los diseños de aplicaciones, ya que los objetos y paquetes se pueden reemplazar con implementaciones alternativas, siempre y cuando se mantenga la misma interfaz.

En las clases, la encapsulación se logra mediante la limitación del acceso externo al estado interno de la clase. Si un actor externo quiere manipular el estado del objeto, deberá hacerlo a través de una función bien definida (o un establecedor de propiedades), en lugar de tener acceso directo al estado privado del objeto. Del mismo modo, los componentes de aplicación y las propias aplicaciones deben exponer interfaces bien definidas para que sus colaboradores las usen, en lugar de permitir que su estado se modifique directamente. Esto libera el diseño interno de la aplicación para que evolucione con el tiempo sin tener que preocuparse de si al hacerlo afectará a los colaboradores, siempre y cuando se mantengan los contratos públicos.

### <a name="dependency-inversion"></a>Inversión de dependencias

La dirección de dependencia dentro de la aplicación debe estar en la dirección de la abstracción, no de los detalles de implementación. La mayoría de las aplicaciones se escriben de manera que la dependencia de tiempo de compilación fluya en la dirección de ejecución del tiempo de ejecución. Esto genera un gráfico de dependencias directas. Es decir, si el módulo A llama a una función en el módulo B, que llama a una función en el módulo C, A dependerá en tiempo de compilación de B, que a su vez dependerá de C, como se muestra en la figura 4-1.

![Gráfico de dependencias directas](./media/image4-1.png)

**Figura 4-1.** Gráfico de dependencias directas.

Aplicar el principio de inversión de dependencias permite que A llame a métodos en una abstracción que implementa B, lo que hace posible que A llame a B en tiempo de ejecución, pero que B dependa de una interfaz controlada por A en tiempo de compilación (por tanto, se *invierte* la dependencia de tiempo de compilación normal). En tiempo de ejecución, el flujo de ejecución del programa no cambia, pero la introducción de interfaces significa que se pueden conectar fácilmente otras implementaciones de estas interfaces.

![Gráfico de dependencias invertidas](./media/image4-2.png)

**Figura 4-2.** Gráfico de dependencias invertidas.

La **Inversión de dependencias** es una parte fundamental de la creación de aplicaciones de acoplamiento flexible, ya que se pueden escribir detalles de implementación de los que depender e implementar abstracciones de nivel superior, en lugar de hacerlo al revés. Como resultado, las aplicaciones son modulares y más fáciles de probar y mantener. La práctica de la *inserción de dependencias* es posible si se sigue el principio de inversión de dependencias.

### <a name="explicit-dependencies"></a>Dependencias explícitas

**Los métodos y las clases deben requerir explícitamente todos los objetos de colaboración que necesiten para funcionar correctamente.** Los constructores de clases proporcionan una oportunidad para que las clases identifiquen lo que necesitan para poder tener un estado válido y funcionar correctamente. Si se definen clases que se pueden construir y a las que se puede llamar, pero que solo funcionarán correctamente si existen determinados componentes globales o de infraestructura, estas clases *no estarán siendo honestas* con sus clientes. El contrato de constructor indica al cliente que solo necesita los elementos especificados (posiblemente ninguno si la clase solo usa un constructor sin parámetros), pero después, en tiempo de ejecución, en realidad el objeto necesita algo más.

Si siguen el principio de dependencias explícitas, las clases y métodos estarán siendo sinceros con sus clientes con respecto a lo que necesitan para poder funcionar. Esto hace que el código sea más autoexplicativo y los contratos de codificación más fáciles de usar, puesto que los usuarios confiarán en eso siempre que proporcionen lo que se necesita en forma de parámetros de método o constructor, los objetos con los trabajan se comportarán correctamente en tiempo de ejecución.

### <a name="single-responsibility"></a>Responsabilidad única

El principio de responsabilidad única se aplica al diseño orientado a objetos, pero también se puede considerar como un principio de arquitectura similar a la separación de intereses. Indica que los objetos solo deben tener una responsabilidad y solo una razón para cambiar. En concreto, la única situación en la que el objeto debe cambiar es si hay que actualizar la manera en la que lleva a cabo su única responsabilidad. El hecho de seguir este principio ayuda a generar sistemas más modulares y de acoplamiento flexible, dado que muchos tipos de comportamientos nuevos se pueden implementar como clases nuevas, en lugar de mediante la incorporación de responsabilidad adicional a las clases existentes. Agregar clases nuevas siempre es más seguro que cambiar las existentes, puesto que todavía no hay código que dependa de las clases nuevas.

En una aplicación monolítica, se puede aplicar el principio de responsabilidad única en un nivel general a las capas de la aplicación. La responsabilidad de la presentación debe mantenerse en el proyecto de la interfaz de usuario, mientras que la responsabilidad de acceso a los datos se debe mantener en un proyecto de infraestructura. La lógica de negocios se debe mantener en el proyecto principal de la aplicación, donde se puede probar fácilmente y puede evolucionar con independencia de otras responsabilidades.

Cuando este principio se aplica a la arquitectura de la aplicación y se lleva a su punto de conexión lógico, se obtienen microservicios. Un microservicio determinado debe tener una sola responsabilidad. Si es necesario extender el comportamiento de un sistema, es mejor hacerlo agregando otros microservicios, en lugar de agregar responsabilidad a uno ya existente.

[Más información sobre la arquitectura de microservicios](https://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>Una vez y solo una (DRY)

La aplicación debe evitar especificar el comportamiento relacionado con un determinado concepto en varios lugares, ya que esto es una fuente de errores frecuente. En algún momento, un cambio en los requisitos requerirá cambiar este comportamiento. Es probable que al menos una instancia del comportamiento no se pueda actualizar, y se producirá un comportamiento incoherente del sistema.

En lugar de duplicar la lógica, se puede encapsular en una construcción de programación. Convierta esta construcción en la única autoridad sobre este comportamiento y haga que cualquier otro elemento de la aplicación que requiera este comportamiento use la nueva construcción.

> [!NOTE]
> Evite el enlace conjunto del comportamiento que solo se repita de forma causal. Por ejemplo, solo porque dos constantes diferentes tengan el mismo valor no significa que debería tener solo una constante, si conceptualmente se refieren a cosas diferentes.

### <a name="persistence-ignorance"></a>Omisión de persistencia

La **Omisión de persistencia** (PI) hace referencia a los tipos que se deben conservar, pero cuyo código no se ve afectado por la elección de la tecnología de persistencia. En .NET, estos tipos a veces se denominan objeto CRL estándar (POCO), ya que no necesitan heredar de una clase base concreta o implementar una interfaz determinada. La omisión de persistencia es útil porque permite conservar el mismo modelo de negocio de varias formas, lo que ofrece flexibilidad adicional a la aplicación. Es posible que las opciones de persistencia cambien con el tiempo, de una tecnología de base de datos a otra, o bien que se necesiten otras formas de persistencia además de las iniciales de la aplicación (por ejemplo, el uso de una caché en Redis o Azure Cosmos DB además de un base de datos relacional).

Algunos ejemplos de las infracciones de este principio son estos:

- Una clase base requerida.

- Una implementación de interfaz requerida.

- Clases responsables de guardarse a sí mismas (por ejemplo, el patrón de registro activo).

- Constructor sin parámetros requerido.

- Propiedades que requieren la palabra clave virtual.

- Atributos requeridos específicos de la persistencia.

El requisito de que las clases tengan cualquiera de las características o comportamientos anteriores agrega acoplamiento entre los tipos que se deben conservar y la elección de la tecnología de persistencia, lo que dificulta la adopción de nuevas estrategias de acceso de datos en el futuro.

### <a name="bounded-contexts"></a>Contextos delimitados

Los **contextos delimitados** son un patrón esencial en el diseño controlado por dominios. Proporcionan una manera de abordar la complejidad en organizaciones o aplicaciones de gran tamaño dividiéndola en módulos conceptuales independientes. Después, cada módulo conceptual representa un contexto que está separado de otros contextos (por tanto, delimitado) y que puede evolucionar independientemente. Idealmente, cada contexto delimitado debería poder elegir sus propios nombres para los conceptos que contiene y tener acceso exclusivo a su propio almacén de persistencia.

Como mínimo, las aplicaciones web individuales deberían intentar ser su propio contexto delimitado, con su propio almacén de persistencia para su modelo de negocios, en lugar de compartir una base de datos con otras aplicaciones. La comunicación entre los contextos delimitados se realiza a través de interfaces de programación, en lugar de una base de datos compartida, lo que permite que la lógica de negocios y los eventos se produzcan en respuesta a los cambios que tienen lugar. Los contextos delimitados se asignan estrechamente a los microservicios que, idealmente, también se implementan como sus propios contextos delimitados individuales.

## <a name="additional-resources"></a>Recursos adicionales

- [Patrones de diseño de JAVA: principios](https://java-design-patterns.com/principles/)
- [Bounded Context](https://martinfowler.com/bliki/BoundedContext.html) (Contexto delimitado)

>[!div class="step-by-step"]
>[Anterior](choose-between-traditional-web-and-single-page-apps.md)
>[Siguiente](common-web-application-architectures.md)
