---
title: Principios de la arquitectura
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | Principios de la arquitectura"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: 20524c8aa0e64fd40a1a4a6811063557f74074d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
#<a name="architectural-principles"></a>Principios de la arquitectura

> "Si generadores generan edificios los programadores de la manera de escribir programas, a continuación, el primer pájaro carpintero suministrada a lo largo de destruiría civilización."  
> _\-Gerald Weinberg_

## <a name="summary"></a>Resumen

Se debe diseñar la arquitectura y las soluciones de software con facilidad de mantenimiento de cuenta. Los principios que se describen en esta sección le ayudarán en las decisiones arquitectónicas que dará como resultado en aplicaciones limpias y fácil de mantener. Por lo general, estos principios le ayudará a generar aplicaciones fuera crea componentes discretos que aún no están estrechamente relacionadas con otras partes de la aplicación, pero en su lugar se comunican a través de interfaces explícitas o sistemas de mensajería.

## <a name="common-design-principles"></a>Principios de diseño comunes

### <a name="separation-of-concerns"></a>Separación de intereses

Es un principio fundamental al desarrollar **separación de asuntos**. Este principio afirma que el software debe estar separado en función de los tipos de trabajo que realiza. Por ejemplo, considere una aplicación que incluye la lógica para identificar los elementos de interés para mostrar al usuario y que da formato a estos elementos de una manera determinada para hacerlos más evidentes. El comportamiento del responsable de elegir los elementos que desea dar formato deben mantenerse separados del comportamiento responsable de dar formato a los elementos, puesto que éstas son preocupaciones independientes que solo casualmente se relacionan entre sí.

Su arquitectura, las aplicaciones pueden crearse lógicamente para seguir este principio mediante la separación de comportamiento de negocios básico de lógica de la interfaz de usuario y la infraestructura. Idealmente, lógica y reglas de negocios deben residir en un proyecto independiente, que no debe depender de otros proyectos de la aplicación. Esto ayuda a garantizar que el modelo de negocio es fácil probar y pueden evolucionar sin que se está estrechamente a detalles de implementación de bajo nivel. Separación de intereses es una consideración clave detrás de la utilización de las capas en arquitecturas de aplicación.

### <a name="encapsulation"></a>Encapsulación

Diferentes partes de una aplicación deben utilizar **encapsulación** para aislarlos de otras partes de la aplicación. Deben poder ajustar su implementación interna sin interrumpir sus colaboradores como contratos externos no se infrinjan las capas y componentes de la aplicación. Uso correcto de encapsulación contribuye a lograr acoplamiento flexible y modularidad en diseños de aplicaciones, ya que los objetos y los paquetes pueden reemplazarse con implementaciones alternativas, siempre y cuando se mantiene la misma interfaz.

En las clases, encapsulación se logra mediante la limitación de fuera de acceso al estado interno de la clase. Si desea que un actor externo manipular el estado del objeto, deberá hacerlo a través de una función bien definida (o establecedor de propiedades), en lugar de tener acceso directo al estado privado del objeto. Del mismo modo, los componentes de aplicación y las mismas aplicaciones deben exponer interfaces bien definidas para los colaboradores a la utilice, en lugar de permitir su estado a modificarse directamente. Esto libera el diseño interno de la aplicación para evolucionar con el tiempo sin tener en cuenta que al hacerlo así interrumpirá colaboradores, siempre y cuando se mantienen los contratos públicos.

### <a name="dependency-inversion"></a>Inversión de dependencia

La dirección de dependencia dentro de la aplicación debe estar en la dirección de abstracción, no los detalles de implementación. Mayoría de las aplicaciones se escribe de manera que fluya de dependencia de tiempo de compilación en la dirección de tiempo de ejecución. Esto genera un gráfico de dependencias directas. Es decir, si llama a módulo A una función en el módulo B, que llama a una función en el módulo C, a continuación, según se desee de un tiempo de compilación depende de B que dependerá de C, como se muestra en la figura 4-1.

![](./media/image4-1.png)

**Figura 4-1.** Gráfico de dependencia directa.

Aplicar el principio de la inversión de dependencia permite A llamar a métodos en una abstracción que implementa B, que hace posible para una llamada B en tiempo de ejecución, pero por B dependen de una interfaz controla un en tiempo de compilación (por lo tanto, *invertir* la dependencia tiempo de compilación normal). En tiempo de ejecución, no cambie el flujo de ejecución del programa, pero la introducción de interfaces significa que las implementaciones diferentes de estas interfaces se pueden conectar fácilmente.

![](./media/image4-2.png)

**Figura 4-2.** Gráfico de dependencias invertido.

**Inversión de dependencia** es una parte fundamental de la creación de aplicaciones de acoplamiento flexible, ya que se pueden escribir detalles de implementación dependen e implementar abstracciones de nivel superior, en lugar de al revés. Las aplicaciones resultantes son comprobables, modular y fácil de mantener como resultado. La práctica de *inyección de dependencia* se realiza mediante sigue el principio de la inversión de dependencia.

### <a name="explicit-dependencies"></a>Dependencias explícitas

**Clases y métodos necesario explícitamente los objetos de colaboración que necesiten para funcionar correctamente.** Los constructores de clases proporcionan una oportunidad para que las clases identificar lo que necesitan para poder participar en un estado válido y funcione correctamente. Si se definen las clases que se puede construir y recibir llamadas, pero que sólo funcionará correctamente si son ciertos componentes de infraestructura o globales en su lugar, estas clases se están *malas intenciones* con sus clientes. El contrato de constructor indica el cliente que solo necesita las cosas especificadas (posiblemente nada si la clase simplemente está utilizando un constructor predeterminado), pero, a continuación, en tiempo de ejecución convierte el objeto realmente necesita algo más.

Si sigue el principio de dependencias explícitas, las clases y métodos se están sinceros con sus clientes acerca de lo necesitan para poder funcionar. Esto hace que su código autoexplicativo más y la codificación de contratos más fácil de usar, puesto que procederán a los usuarios confiar siempre que proporcionan lo que se necesita en el formulario del método o parámetros del constructor, los objetos que trabajará con se comportarán correctamente en tiempo de ejecución.

### <a name="single-responsibility"></a>Responsabilidad única

El principio de responsabilidad solo se aplica al diseño orientado a objetos, pero también puede considerarse como un principio arquitectura similar a la separación de intereses. Indica que los objetos deben tener solo una de las responsabilidades y que debe tener solo una de las razones para cambiar. En concreto, la única situación en la que debe cambiar el objeto es si debe actualizarse la manera en la que lleva a cabo su uno responsabilidad. Siguiendo este principio ayuda a generar más acoplamiento flexible y sistemas modulares, desde muchos tipos de comportamiento nuevo pueden implementarse como clases nuevas, en lugar de mediante la adición de responsabilidad adicional a las clases existentes. Agregar nuevas clases siempre es más seguro que cambiar las clases existentes, puesto que ningún código aún depende de las nuevas clases.

En una aplicación monolítica, podemos aplicar el principio de responsabilidad única a un alto nivel en las capas de la aplicación. Responsabilidad de presentación debe permanecer en el proyecto de la interfaz de usuario, mientras que acceden datos responsabilidad debe mantenerse en un proyecto de infraestructura. Lógica de negocios se debe mantener en el proyecto de núcleo de aplicación, donde se puede probar fácilmente y pueden evolucionar independientemente de otras responsabilidades.

Cuando este principio se aplica a la arquitectura de la aplicación y se tarda en su extremo lógico, obtendrá microservicios. Un microservicio determinado debe tener una sola responsabilidad. Si necesita extender el comportamiento de un sistema, es mejor hacerlo agregando microservicios adicionales, en lugar de mediante la adición de responsabilidad a otro existente.

[Más información acerca de la arquitectura de microservicios](http://aka.ms/MicroservicesEbook)

### <a name="dont-repeat-yourself-dry"></a>No repita usted mismo (SECA)

La aplicación se deben especificar el comportamiento relacionado con un determinado concepto en varios lugares tal y como se trata de un origen de errores frecuente. En algún momento, será necesario un cambio en los requisitos de cambiar este comportamiento y la probabilidad de que al menos una instancia del comportamiento se producirá un error al actualizar se producirá un comportamiento incoherente del sistema.

En lugar de duplicar lógica, encapsularlo en una construcción de programación. Convertir en construir la única entidad sobre este comportamiento, y que cualquier otra parte de la aplicación que requiere este comportamiento, utilice la construcción de nuevo.

> [!NOTE]
> Evite juntos enlace comportamiento que solo casualmente repetitivo. Por ejemplo, solo porque dos constantes diferentes ambos tienen el mismo valor, eso no significa que debería tener sólo una constante, si conceptualmente nos referimos a cosas diferentes.

### <a name="persistence-ignorance"></a>Omisión de persistencia

**Omisión de persistencia** (PI) hace referencia a tipos que deban conservarse, pero cuyo código se ve afectado por la elección de la tecnología de persistencia. Estos tipos en .NET a veces se conocen como objetos de CLR antiguos sin formato (POCOs), ya que no es necesario heredar de una clase base concreta o implementar una interfaz determinada. Omisión de persistencia es útil porque permite el mismo modelo de negocio debe conservarse en varias formas, que ofrece flexibilidad adicional a la aplicación. Pueden cambiar las opciones de persistencia con el tiempo, de tecnología de una base de datos a otro, o podrían ser necesarios además de lo que inicia la aplicación con otras formas de persistencia (por ejemplo, mediante una caché en Redis o documentos de Azure además un base de datos relacional).

Algunos ejemplos de las infracciones de este principio:

-   Una clase base requerida

-   Una implementación de interfaz necesaria

-   Clases responsables de por sí mismos guardar (por ejemplo, el patrón de registro activo)

-   Constructor predeterminado requerido

-   Propiedades que requieren la palabra clave virtual

-   Atributos requeridos específicos de persistencia

El requisito de que las clases tengan cualquiera de las características o comportamientos anterior agrega acoplamiento entre los tipos que se deben conservar y la elección de la tecnología de persistencia, lo que dificulta a adoptar nuevas estrategias de acceso de datos en el futuro.

### <a name="bounded-contexts"></a>Contextos de límites

**Limitado contextos** son un patrón de diseño de Domain-Driven central. Proporcionan una manera de complejidad de abordar en aplicaciones de gran tamaño u organizaciones por dividirlo en módulos conceptuales. Cada módulo conceptual, a continuación, representa un contexto que está separado de otros contextos (por lo tanto, limitado) y pueden evolucionar independientemente. Cada contexto enlazado lo ideal es que se deben elegir sus propios nombres de conceptos dentro de él y debe tener acceso exclusivo a su propio almacén de persistencia.

Como mínimo, deben procurar aplicaciones web individuales como su propio contexto enlazado, con su propio almacén de persistencia para su modelo de negocios, en lugar de una base de datos de uso compartido con otras aplicaciones. Se produce la comunicación entre contextos enlazados a través de interfaces de programación, en lugar de a través de una base de datos compartido, que permite la lógica de negocios y eventos pueda colocar en respuesta a los cambios que tienen lugar. Limitado contextos mapa estrechamente a microservicios, que también lo ideal es que se implementan como sus propios contextos enlazados individuales.

> ### <a name="references--modern-web-applications"></a>Referencias: aplicaciones Web modernas
> - **Separación de intereses**  
> <http://deviq.com/Separation-of-Concerns/>
> - **Encapsulación** <http://deviq.com/encapsulation/>
> - **Principio de la inversión de dependencia**  
> <http://deviq.com/Dependency-inversion-Principle/>
> - **Principio de dependencias explícitas**  
> <http://deviq.com/Explicit-Dependencies-Principle/>
> - **No repita usted mismo**  
> <http://deviq.com/Don-t-Repeat-Yourself/>
> - **Omisión de persistencia**  
> <http://deviq.com/Persistence-ignorance/>
> - **Contexto enlazado**  
> <https://martinfowler.com/bliki/BoundedContext.HTML>

> [!div class="step-by-step"]
[Anterior] (choose-between-traditional-web-and-single-page-apps.md) [siguiente] (común-web-aplicaciones-architectures.md)
