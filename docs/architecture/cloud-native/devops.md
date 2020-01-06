---
title: DevOps nativa de la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | DevOps nativa de la nube
ms.date: 06/30/2019
ms.openlocfilehash: d152989061964d78c8be97b69df413b975058319
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337411"
---
# <a name="cloud-native-devops"></a>DevOps nativa de la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

El mantr favorito de los asesores de software es responder "depende" de cualquier pregunta planteada. No se debe a que los consultores de software no toman ninguna posición. Esto se debe a que no hay ninguna respuesta auténtica a las preguntas del software. No hay ningún derecho absoluto y incorrecto, sino un equilibrio entre los opuestos.

Tomemos, por ejemplo, las dos escuelas principales del desarrollo de aplicaciones web: aplicaciones de una sola página (Spa) frente a aplicaciones del lado servidor. Por un lado, la experiencia del usuario tiende a ser mejor con spa y la cantidad de tráfico al servidor Web se puede minimizar, lo que permite hospedarlos en algo tan sencillo como el hospedaje estático. Por otro lado, los Spa suelen ser más lentos de desarrollar y más difíciles de probar. ¿Cuál es la opción correcta? Bien, depende de su situación.

Las aplicaciones nativas de la nube no son inmunes a ese mismo Dichotomy. Tienen ventajas claras en cuanto a la velocidad del desarrollo, la estabilidad y la escalabilidad, pero administrarlos puede ser un poco más difícil.

Hace años, no era raro que el proceso de mover una aplicación de desarrollo a producción tomara un mes, o incluso más. Las empresas publican software en un ritmo de 6 meses o incluso cada año. No es necesario que Microsoft Windows se parezca más a la cadencia de las versiones que eran aceptables antes de los días de la marcha de Windows 10. Cinco años transcurridos entre Windows XP y vista, más de 3 entre vista y Windows 7.

Ahora está bien establecido que poder lanzar software rápidamente ofrece a las empresas una gran ventaja en el mercado con respecto a sus competidores más sloths. Por ese motivo, las actualizaciones principales de Windows 10 son aproximadamente cada seis meses.

Los patrones y prácticas que permiten que las versiones más rápidas y confiables entreguen valor a la empresa se conocen colectivamente como DevOps. Están formados por una amplia gama de ideas que abarcan todo el ciclo de vida de desarrollo de software desde la especificación de una aplicación hasta la entrega y el funcionamiento de la aplicación.

DevOps surgió antes que los microservicios y es probable que el movimiento hacia los servicios de propósito más pequeños, más ajustados a los fines, no hubiera sido posible sin DevOps para que la liberación y el funcionamiento no solo de una pero muchas aplicaciones en producción fuera más fácil.

![La figura 11-0 las tendencias de búsqueda muestran que el crecimiento de los microservicios no se inicia hasta que DevOps es una idea bastante bien establecida.](./media/microservices-vs-devops.png)

Gracias a las buenas prácticas de DevOps, es posible obtener las ventajas de las aplicaciones nativas de la nube sin Suffocating con una montaña de trabajo que realmente funcione con las aplicaciones.

No hay ningún martillo de oro en cuanto a DevOps. Nadie puede vender una solución completa y completa para lanzar y operar aplicaciones de alta calidad. Esto se debe a que cada aplicación es muy diferente de las demás. Sin embargo, hay herramientas que pueden hacer que DevOps sea una propuesta mucho menos desalentadora. Una de estas herramientas se conoce como DevOps de Azure.

## <a name="azure-devops"></a>Azure DevOps

Azure DevOps tiene un pedigrí largo. Puede volver a hacer un seguimiento de sus raíces cuando Team Foundation Server por primera vez en línea y a través de los distintos cambios de nombre: Visual Studio online y Visual Studio Team Services. Sin embargo, a lo largo de los años, ha llegado mucho más allá de sus predecesores.

Azure DevOps se divide en cinco componentes principales:

![Figura 11-1 las cinco áreas principales de DevOps de Azure](./media/devops-components.png)

**Azure Boards** : proporciona un problema y una herramienta de seguimiento de elementos de trabajo que se esfuerza por permitir que los usuarios elijan los flujos de trabajo que mejor funcionan para ellos. Incluye varias plantillas preconfiguradas, como las que admiten los estilos SCRUM y Kanban de desarrollo.

**Azure Repos** : administración de código fuente que admite el control de versiones de Team Foundation venerable (TFVC) y el git favorito del sector. Las solicitudes de incorporación de cambios proporcionan una manera de habilitar la codificación social fomentando la explicación de los cambios a medida que se realizan.

**Azure pipelines** -un sistema de administración de versión y compilación que admita una estrecha integración con Azure. Las compilaciones se pueden ejecutar en una gran variedad de plataformas de Windows a Linux y MacOS. Los agentes de compilación se pueden aprovisionar en la nube o de forma local.

**Azure Test Plans** : no se dejará ninguna persona de control de calidad con la compatibilidad con la administración de pruebas y las pruebas exploratorias que ofrece la característica Test Plans.

**Azure Artifacts** : una fuente de artefactos que permite a las empresas crear sus propias versiones, internas, de NuGet, NPM y otras. Sirve para un doble propósito de actuar como una caché de paquetes ascendentes si se produce un error en un repositorio centralizado.

La unidad organizativa de nivel superior de Azure DevOps se denomina proyecto. Dentro de cada proyecto, los distintos componentes, como Azure Artifacts, pueden activarse y desactivarse. Si los usuarios desean administrar su código fuente en GitHub pero siguen aprovechando Azure Pipelines, eso es perfectamente posible. De hecho, muchos proyectos de código abierto aprovechan las [compilaciones gratuitas](https://azure.microsoft.com/blog/announcing-azure-pipelines-with-unlimited-ci-cd-minutes-for-open-source/) que ofrece Azure DevOps mientras mantienen su código fuente en github. Algunos proyectos de código abierto significativos como [Visual Studio Code](https://code.visualstudio.com/), [hilados](https://yarnpkg.com/en/), [Gulp](https://gulpjs.com/)y [NumPy](https://www.numpy.org/) han realizado la transición.

Cada uno de estos componentes proporciona algunas ventajas para las aplicaciones nativas de la nube, pero las tres más útiles son el control de código fuente, las placas y las canalizaciones.  

## <a name="source-control"></a>Control de código fuente

La organización del código para una aplicación nativa en la nube puede resultar complicada. En lugar de una sola aplicación gigante, las aplicaciones nativas de la nube tienden a estar compuestas de una web de aplicaciones más pequeñas que se comunican entre sí. Al igual que sucede con todo lo que hay en informática, la mejor disposición del código sigue siendo una pregunta abierta. Hay ejemplos de aplicaciones correctas que usan diferentes tipos de diseños, pero parece que dos variantes tienen la mayor popularidad.

Antes de llegar al propio control de código fuente real, probablemente merece la pena decidir cuántos proyectos son adecuados. Dentro de un solo proyecto, hay compatibilidad con varios repositorios y canalizaciones de compilación. Los paneles son un poco más complicados, pero también se pueden asignar fácilmente a varios equipos dentro de un solo proyecto. Es ciertamente posible admitir cientos, incluso miles de desarrolladores, de un solo proyecto de Azure DevOps. Hacerlo es probablemente el mejor enfoque, ya que proporciona un único lugar para que todo el desarrollador pueda trabajar y reduzca la confusión que supone encontrar una aplicación cuando los desarrolladores no están seguros del proyecto en el que reside.

Dividir el código para los microservicios dentro del proyecto DevOps de Azure puede ser un poco más desafiante.

![Figura 11-2 única frente a varios repositorios](./media/single-repository-vs-multiple.png)

### <a name="repository-per-microservice"></a>Repositorio por microservicio

A primera vista, parece como el enfoque más lógico para dividir el código fuente de los microservicios. Cada repositorio puede contener el código necesario para compilar un microservicio. Las ventajas de este enfoque son fácilmente visibles:

1. Las instrucciones para generar y mantener la aplicación se pueden agregar a un archivo Léame en la raíz de cada repositorio. Al voltear los repositorios, es fácil encontrar estas instrucciones, lo que reduce el tiempo de arranque de los desarrolladores.
2. Cada servicio se encuentra en un lugar lógico y se encuentra fácilmente conociendo el nombre del servicio.
3. Las compilaciones se pueden configurar fácilmente de forma que solo se desencadenen cuando se realiza un cambio en el repositorio propietario.
4. El número de cambios que entran en un repositorio se limita al número reducido de desarrolladores que trabajan en el proyecto.
5. La seguridad es fácil de configurar mediante la restricción de los repositorios a los que los desarrolladores tienen permisos de lectura y escritura.
6. El equipo propietario puede cambiar la configuración de nivel de repositorio con un mínimo de debate con otras personas.

Una de las ideas clave detrás de los microservicios es que los servicios se deben silor y separar entre sí. Al usar el diseño basado en dominio para decidir los límites de los servicios, los servicios actúan como límites transaccionales. Las actualizaciones de base de datos no deben abarcar varios servicios. Esta colección de datos relacionados se conoce como contexto delimitado.  Esta idea se refleja en el aislamiento de los datos de microservicios a una base de datos independiente y autónoma del resto de los servicios. Le resultará muy útil llevar esta idea a través del código fuente de.

Sin embargo, este enfoque no está sin sus problemas. Uno de los problemas de desarrollo más gnarly de nuestro tiempo es la administración de las dependencias. Tenga en cuenta el número de archivos que componen el promedio `node_modules` directorio. Una instalación nueva de algo como `create-react-app` es probable que incorpore miles de paquetes. La cuestión de cómo administrar estas dependencias es difícil.

Si se actualiza una dependencia, los paquetes de nivel inferior también deben actualizar esta dependencia. Desafortunadamente, eso lleva el trabajo de desarrollo, de forma invariable, el directorio de `node_modules` finaliza con varias versiones de un único paquete, cada una de las cuales es una dependencia de algún otro paquete con versiones de una cadencia ligeramente diferente. Al implementar una aplicación, ¿qué versión de una dependencia debe usarse? ¿La versión que está actualmente en producción? La versión que se encuentra actualmente en versión beta, pero que es probable que esté en producción en el momento en que el consumidor la convierte en producción. Problemas difíciles que no se resuelven mediante el uso de microservicios.

Hay bibliotecas que dependen de una amplia variedad de proyectos. Al dividir los microservicios con uno en cada repositorio, las dependencias internas se pueden resolver mejor mediante el repositorio interno, Azure Artifacts. Las compilaciones de las bibliotecas incorporarán sus versiones más recientes en Azure Artifacts para el consumo interno. El proyecto de nivel inferior debe actualizarse manualmente para que dependa de los paquetes recién actualizados.

Otro inconveniente se presenta al mover el código entre los servicios. Aunque sería bueno creer que la primera división de una aplicación en microservicios es 100% correcta, la realidad es que rara vez estamos prescient como para no cometer errores de división de servicios. Por lo tanto, la funcionalidad y el código que lo impulsa deberán moverse de servicio a servicio: repositorio al repositorio. Al hacer un salto de un repositorio a otro, el código pierde el historial. Hay muchos casos, especialmente en el caso de una auditoría, donde el historial completo de un fragmento de código es muy valioso.

La desventaja final y quizás más importante es la coordinación de los cambios. En una aplicación de microservicios verdadera, no debería haber dependencias de implementación entre los servicios. Debe ser posible implementar los servicios A, B y C en cualquier orden, ya que tienen acoplamiento flexible. Sin embargo, en realidad, hay ocasiones en las que es deseable hacer un cambio que cruce varios repositorios al mismo tiempo. Algunos ejemplos incluyen la actualización de una biblioteca para cerrar un agujero de seguridad o el cambio de un protocolo de comunicación utilizado por todos los servicios.

Para realizar un cambio entre repositorios, es necesario realizar una confirmación en cada repositorio en sucesión. Cada cambio de cada repositorio deberá solicitarse y revisarse por separado. Esto puede ser difícil de coordinar y generalmente molesto.

Una alternativa al uso de muchos repositorios es poner todo el código fuente en un gigante, todo ello en un único repositorio.

### <a name="single-repository"></a>Repositorio único

En este enfoque, que a veces se conoce como [monorepositorio](https://danluu.com/monorepo/), todo el código fuente de cada servicio se coloca en el mismo repositorio. En primer lugar, esto parece una idea muy poco probable de hacer que el código fuente no sea manejable. Sin embargo, hay algunas ventajas marcadas para trabajar de esta manera.

La primera ventaja es que es más fácil administrar las dependencias entre proyectos. En lugar de depender de una fuente de artefactos externa, los proyectos pueden importarse directamente. Esto significa que las actualizaciones son instantáneas y que es probable que se encuentren versiones conflictivas en tiempo de compilación en la estación de trabajo del desarrollador. En efecto, se desplazan algunas de las pruebas de integración a la izquierda.

Al mover código entre proyectos, ahora es más fácil conservar el historial, ya que los archivos se detectarán como movidos en lugar de reescribirse.

Otra ventaja es que los cambios que varían en los límites de servicio pueden realizarse en una sola confirmación. Esto reduce la sobrecarga que supone tener que revisar los cambios de forma individual.

Hay muchas herramientas que pueden realizar análisis estáticos de código para detectar prácticas de programación no seguras o el uso problemático de las API. En un mundo con varios repositorios, cada repositorio deberá recorrer en iteración para encontrar los problemas en ellos. El repositorio único permite ejecutar el análisis en un solo lugar.

También hay muchas desventajas en el enfoque de repositorio único. Uno de los más preocupados es que tener un único repositorio genera problemas de seguridad. Si el contenido de un repositorio se pierde en un repositorio por cada modelo de servicio, la cantidad de código perdido es mínima. Con un único repositorio, se podría perder todo lo que posea la compañía. En el pasado, hemos habido muchos ejemplos en los que se entrenó todo el trabajo de desarrollo de juegos. El hecho de tener varios repositorios expone menos área expuesta, que es un rasgo muy deseable en la mayoría de los procedimientos de seguridad.

Es probable que el tamaño del único repositorio deje de ser fácil de administrar. Esto presenta algunas implicaciones interesantes en el rendimiento. Puede ser necesario usar herramientas especializadas como el [sistema de archivos virtual para git](https://vfsforgit.org/), que se diseñó originalmente para mejorar la experiencia de los desarrolladores en el equipo de Windows.

Con frecuencia, el argumento para usar un único repositorio se reduce a un argumento que Facebook o Google usan este método para la organización del código fuente. Si el enfoque es lo suficientemente bueno para estas empresas, seguramente es el enfoque correcto para todas las empresas. La verdad de la cuestión es que muy pocas empresas operan en algo como la escala de Facebook o Google. Los problemas que se producen en esas escalas son diferentes de los que se verán en la mayoría de los desarrolladores. Lo que es adecuado para el OCA no puede ser bueno para el Gander.

Al final, cualquiera de las soluciones se puede usar para hospedar el código fuente de los microservicios. Sin embargo, en la mayoría de los casos, la sobrecarga de administración y Ingeniería de trabajar en un único repositorio no merece las ventajas de Meager. Al dividir el código en varios repositorios, se fomenta una mejor separación de problemas y se fomenta la autonomía entre los equipos de desarrollo.  

### <a name="standard-directory-structure"></a>Estructura de directorios estándar

Sin tener en cuenta el debate entre varios repositorios, cada servicio tendrá su propio directorio. Una de las mejores optimizaciones que permiten a los desarrolladores cruzar entre proyectos rápidamente es mantener una estructura de directorios estándar.

![Figura 11-3 una estructura de directorios estándar para el correo electrónico y los servicios de inicio de sesión](./media/dir-struct.png)

Cada vez que se crea un nuevo proyecto, se debe usar una plantilla que coloque la estructura correcta. Esta plantilla también puede incluir elementos útiles como un archivo Léame de esqueleto y un `azure-pipelines.yml`. En cualquier arquitectura de microservicios, un alto grado de varianza entre proyectos hace que las operaciones masivas en los servicios sean más difíciles.

Hay muchas herramientas que pueden proporcionar plantillas para un directorio completo, que contiene varios directorios de código fuente. [Yeoman](https://yeoman.io/) es popular en el mundo de JavaScript y GitHub ha publicado recientemente [plantillas de repositorio](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/), que proporcionan gran parte de la misma funcionalidad.

## <a name="task-management"></a>Administración de tareas

La administración de tareas en cualquier proyecto puede ser difícil. Por adelantado, hay innumerables preguntas que se deben responder sobre la ordenación de los flujos de trabajo para garantizar una productividad óptima del desarrollador.

Las aplicaciones nativas de la nube tienden a ser más pequeñas que los productos de software tradicionales o, al menos, están divididas en servicios más pequeños. El seguimiento de problemas o tareas relacionados con estos servicios permanece tan importante como con cualquier otro proyecto de software. Nadie desea perder el seguimiento de algún elemento de trabajo o explicar a un cliente que su problema no se ha registrado correctamente. Los paneles se configuran en el nivel de proyecto, pero dentro de cada proyecto se pueden definir áreas. Estos permiten desglosar problemas en varios componentes. La ventaja de mantener todo el trabajo para toda la aplicación en un solo lugar es que es fácil trasladar los elementos de trabajo de un equipo a otro a medida que se entienden mejor.

Azure DevOps incluye una serie de plantillas populares preconfiguradas. En la configuración más básica, todo lo que se necesita saber es lo que hay en el trabajo pendiente, en qué personas trabajan y qué se ha hecho. Es importante tener esta visibilidad en el proceso de creación de software, de modo que se pueda priorizar el trabajo y completar las tareas que se notifiquen al cliente. Por supuesto, muy pocos proyectos de software se adhieren a un proceso tan sencillo como `to do`, `doing`y `done`. Los usuarios no tardan mucho en empezar a agregar pasos como `QA` o `Detailed Specification` al proceso.

Una de las partes más importantes de las metodologías ágiles es introspección a intervalos regulares. Estas revisiones están diseñadas para proporcionar información sobre los problemas de cara al equipo y cómo se pueden mejorar. Con frecuencia, esto significa cambiar el flujo de problemas y características a través del proceso de desarrollo. Por lo tanto, es absolutamente correcto expandir los diseños de los paneles con fases adicionales.

Las fases de los paneles no son la única herramienta de la organización. En función de la configuración del panel, hay una jerarquía de elementos de trabajo. El elemento más granular que puede aparecer en un panel es una tarea. De forma automática, una tarea contiene campos para un título, una descripción, una prioridad, una estimación de la cantidad de trabajo restante y la capacidad de vincular a otros elementos de trabajo o elementos de desarrollo (ramas, confirmaciones, solicitudes de incorporación de cambios, compilaciones, etc.). Los elementos de trabajo se pueden clasificar en diferentes áreas de la aplicación y distintas iteraciones (sprints) para facilitar su búsqueda.

![Figura 11-4 una tarea de ejemplo en Azure DevOps](./media/task-details.png)

El campo de Descripción admite los estilos normales que cabría esperar (negrita, carácter de subrayado en cursiva y tachado) y la capacidad de insertar imágenes. Esto lo convierte en una herramienta muy eficaz para su uso al especificar el trabajo o los errores.

Las tareas se pueden acumular en características, que definen una unidad de trabajo mayor. A su vez, las características se pueden [acumular en epopeyas](https://docs.microsoft.com/azure/devops/boards/backlogs/define-features-epics?view=azure-devops). La clasificación de tareas en esta jerarquía hace que sea mucho más fácil comprender cómo se va a implementar una característica grande.

![Figura 11-5 tipos de elemento de trabajo configurados de forma predeterminada en la plantilla de proceso básica](./media/board-issue-types.png)

Hay diferentes tipos de vistas en los problemas de Azure Boards. Los elementos que todavía no están programados aparecen en el trabajo pendiente. Desde allí, se pueden asignar a un Sprint. Un Sprint es un cuadro de tiempo durante el cual se espera que se complete una cantidad de trabajo. Este trabajo puede incluir tareas, pero también la resolución de vales. Una vez allí, todo el Sprint puede administrarse desde la sección del panel del Sprint. Esta vista muestra cómo progresa el trabajo e incluye un gráfico de reproducción hacia abajo para dar una estimación de actualización permanente de si el Sprint se realizará correctamente.

![Figura 11-6 un panel con un Sprint definido](./media/sprint-board.png)

En este momento, debe ser evidente que hay una gran potencia en los paneles de Azure DevOps. Para los desarrolladores, hay vistas sencillas de lo que se está trabajando. Para ver las vistas de los jefes de proyecto, así como información general sobre el trabajo existente. Para los administradores, hay muchos informes sobre el reabastecimiento y la capacidad. Desafortunadamente, no hay nada mágico sobre las aplicaciones nativas de la nube que eliminan la necesidad de realizar un seguimiento del trabajo. Pero si debe realizar un seguimiento del trabajo, hay algunos lugares en los que la experiencia es mejor que en Azure DevOps.

## <a name="cicd-pipelines"></a>Canalizaciones de CI/CD

Casi ningún cambio en el ciclo de vida de desarrollo de software ha sido tan revolucionario como la llegada de la integración continua (CI) y la entrega continua (CD). Compilar y ejecutar pruebas automatizadas en el código fuente de un proyecto en cuanto se protege un cambio en detecta errores al principio. Antes de la llegada de las compilaciones de integración continua, no sería raro extraer el código del repositorio y encontrar que no superó las pruebas o incluso no se pudo compilar. Esto provocó una gran cantidad de seguimiento del origen de la interrupción.

Tradicionalmente, la distribución de software en el entorno de producción requería una amplia documentación y una lista de pasos. Cada uno de estos pasos debe realizarse de forma manual en un proceso muy propenso a errores.

![Figura 11-7 una lista de comprobación](./media/checklist.png)

La hermana de integración continua es la entrega continua en la que los paquetes recién compilados se implementan en un entorno. El proceso manual no se puede escalar para que coincida con la velocidad de desarrollo, por lo que la automatización es más importante. Las listas de comprobación se sustituyen por scripts que pueden ejecutar las mismas tareas de forma más rápida y precisa que cualquier persona.

El entorno en el que entrega continua puede ser un entorno de prueba o, como lo hacen muchas grandes empresas de tecnología, podría ser el entorno de producción. Este último requiere una inversión en pruebas de alta calidad que pueden dar la seguridad de que un cambio no va a interrumpir la producción de los usuarios. Del mismo modo que la integración continua detectó problemas en el código, la entrega continua temprana detecta problemas en el proceso de implementación.

La importancia de automatizar el proceso de compilación y entrega se acentúa en las aplicaciones nativas de la nube. Las implementaciones se producen con más frecuencia y en más entornos, por lo que la implementación manual de los bordes es imposible.

### <a name="azure-builds"></a>Compilaciones de Azure

Azure DevOps proporciona un conjunto de herramientas para facilitar la integración y la implementación continuas. Estas herramientas se encuentran en Azure Pipelines. La primera de ellas es Azure compilaciones, que es una herramienta para ejecutar definiciones de compilación basadas en YAML a escala. Los usuarios pueden traer sus propias máquinas de compilación (para si la compilación requiere un entorno de configuración meticulosa) o usar una máquina de un grupo actualizado constantemente de máquinas virtuales hospedadas en Azure. Estos agentes de compilación hospedados se instalan previamente con una amplia gama de herramientas de desarrollo no solo para el desarrollo de .NET, sino también para todo, desde Java hasta Python hasta el desarrollo de iPhone.

DevOps incluye una amplia gama de definiciones de compilación preparadas que se pueden personalizar para cualquier compilación. Las definiciones de compilación se definen en un archivo denominado `azure-pipelines.yml` y se protegen en el repositorio para que puedan tener versiones junto con el código fuente. Esto hace que sea mucho más fácil realizar cambios en la canalización de compilación en una bifurcación, ya que los cambios se pueden proteger solo en esa rama. En la figura 11-8 se muestra un ejemplo `azure-pipelines.yml` para compilar una aplicación Web de ASP.NET en el marco de trabajo completo.

```yml
name: $(rev:r)

variables:
  version: 9.2.0.$(Build.BuildNumber)
  solution: Portals.sln
  artifactName: drop
  buildPlatform: any cpu
  buildConfiguration: release
  
pool:
  name: Hosted VS2017
  demands:
  - msbuild
  - visualstudio
  - vstest

steps:
- task: NuGetToolInstaller@0
  displayName: 'Use NuGet 4.4.1'
  inputs:
    versionSpec: 4.4.1

- task: NuGetCommand@2
  displayName: 'NuGet restore'
  inputs:
    restoreSolution: '$(solution)'

- task: VSBuild@1
  displayName: 'Build solution'
  inputs:
    solution: '$(solution)'
    msbuildArgs: '-p:DeployOnBuild=true -p:WebPublishMethod=Package -p:PackageAsSingleFile=true -p:SkipInvalidConfigurations=true -p:PackageLocation="$(build.artifactstagingdirectory)\\"'
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: VSTest@2
  displayName: 'Test Assemblies'
  inputs:
    testAssemblyVer2: |
     **\$(buildConfiguration)\**\*test*.dll
     !**\obj\**
     !**\*testadapter.dll
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: CopyFiles@2
  displayName: 'Copy UI Test Files to: $(build.artifactstagingdirectory)'
  inputs:
    SourceFolder: UITests
    TargetFolder: '$(build.artifactstagingdirectory)/uitests'

- task: PublishBuildArtifacts@1
  displayName: 'Publish Artifact'
  inputs:
    PathtoPublish: '$(build.artifactstagingdirectory)'
    ArtifactName: '$(artifactName)'
  condition: succeededOrFailed()
```

**Figura 11-8** : ejemplo de Azure-pipelines. yml

Esta definición de compilación usa una serie de tareas integradas que facilitan la creación de compilaciones tan sencillas como la creación de un conjunto de LEGO (más sencillo que el Giant Falcon). Por ejemplo, la tarea de NuGet restaura los paquetes NuGet, mientras que la tarea VSBuild llama a las herramientas de compilación de Visual Studio para realizar la compilación real. Hay cientos de tareas diferentes disponibles en Azure DevOps, con miles de ellas que mantiene la comunidad. Es probable que, independientemente de las tareas de compilación que quiera ejecutar, ya haya creado una.

Las compilaciones se pueden desencadenar manualmente, mediante una operación de protección, una programación o la finalización de otra compilación. En la mayoría de los casos, es conveniente basarse en cada inserción en el repositorio. Las compilaciones se pueden filtrar para que las distintas compilaciones se ejecuten en diferentes partes del repositorio o en distintas ramas. Esto permite escenarios como la ejecución de compilaciones rápidas con pruebas reducidas en las solicitudes de extracción y la ejecución de un conjunto de regresión completo en el tronco cada noche.

El resultado final de una compilación es una colección de archivos conocidos como artefactos de compilación. Estos artefactos se pueden pasar al siguiente paso del proceso de compilación o agregarse a una fuente de artefactos de Azure, para que puedan consumirlos otras compilaciones.

### <a name="azure-devops-releases"></a>Versiones de DevOps de Azure

Las compilaciones se encargan de compilar el software en un paquete que se puede enviar, pero los artefactos todavía tienen que insertarse en un entorno de prueba para completar la entrega continua. Para ello, Azure DevOps usa una herramienta independiente denominada versiones. La herramienta de versiones hace uso de la misma biblioteca de tareas que estaba disponible para la compilación, pero presenta un concepto de "fases". Una fase es un entorno aislado en el que se instala el paquete. Por ejemplo, un producto puede hacer uso de un desarrollo, un QA y un entorno de producción. El código se entrega continuamente en el entorno de desarrollo en el que se pueden ejecutar pruebas automatizadas. Una vez que estas pruebas superan la versión, se mueven al entorno de QA para realizar pruebas manuales. Por último, el código se inserta en producción, donde es visible para todo el mundo.

![Figura 11-9 ejemplo de canalización de versiones con desarrollo, QA y fases de producción](./media/release-pipeline.png)

Cada fase de la compilación se puede desencadenar automáticamente mediante la finalización de la fase anterior. Sin embargo, en muchos casos, esto no es deseable. Mover código a producción podría requerir la aprobación de alguien. La herramienta de versiones admite esto al permitir aprobadores en cada paso de la canalización de versiones. Las reglas se pueden configurar de modo que una persona o un grupo de personas específicas debe cerrar la sesión en una versión antes de que se haga en producción. Estas puertas permiten comprobaciones de calidad manuales y también para el cumplimiento de los requisitos normativos relacionados con el control de lo que entra en producción.

### <a name="everybody-gets-a-build-pipeline"></a>Todos obtienen una canalización de compilación

La configuración de muchas canalizaciones de compilación no supone ningún costo, por lo que es conveniente tener al menos una canalización de compilación por microservicio. Idealmente, los microservicios se pueden implementar de forma independiente en cualquier entorno, por lo que tener cada uno de ellos capaz de lanzarse a través de su propia canalización sin liberar una masa de código no relacionado es perfecto. Cada canalización puede tener su propio conjunto de aprobaciones, lo que permite variaciones en el proceso de compilación para cada servicio.

### <a name="versioning-releases"></a>Versiones de control de versiones

Un inconveniente de usar la funcionalidad de versiones es que no se puede definir en un archivo de `azure-pipelines.yml` protegido. Hay muchas razones por las que es posible que desee hacer esto desde tener definiciones de versión por rama para incluir un esqueleto de versión en la plantilla de proyecto. Afortunadamente, el trabajo está en curso para desplazar algunas de las fases que se admiten en el componente de compilación. Esto se conoce como compilación en varias fases y la [primera versión ya está disponible](https://devblogs.microsoft.com/devops/whats-new-with-azure-pipelines/).

>[!div class="step-by-step"]
>[Anterior](azure-security.md)
>[Siguiente](infrastructure-as-code.md)
