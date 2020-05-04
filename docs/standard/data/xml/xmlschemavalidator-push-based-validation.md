---
title: Validación basada en inserción de XmlSchemaValidator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 6a0cc110c2b8bcd97b9f5c16a344db5a63046353
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709808"
---
# <a name="xmlschemavalidator-push-based-validation"></a><span data-ttu-id="28e13-102">Validación basada en inserción de XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="28e13-102">XmlSchemaValidator Push-Based Validation</span></span>

<span data-ttu-id="28e13-103">La clase <xref:System.Xml.Schema.XmlSchemaValidator> incluye un mecanismo eficiente y de alto rendimiento para validar datos XML con esquemas XML mediante inserción.</span><span class="sxs-lookup"><span data-stu-id="28e13-103">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides an efficient, high-performance mechanism to validate XML data against XML schemas in a push-based manner.</span></span> <span data-ttu-id="28e13-104">Por ejemplo, la clase <xref:System.Xml.Schema.XmlSchemaValidator> le permite validar un conjunto de información XML en el lugar sin tener que serializarla como un documento XML y, a continuación, volver a analizar el documento utilizando un sistema de lectura XML de validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-104">For example, the <xref:System.Xml.Schema.XmlSchemaValidator> class allows you to validate an XML infoset in-place without having to serialize it as an XML document and then reparse the document using a validating XML reader.</span></span>

<span data-ttu-id="28e13-105">La clase <xref:System.Xml.Schema.XmlSchemaValidator> se puede utilizar en situaciones avanzadas como, por ejemplo, durante la creación de motores de validación en orígenes de datos XML o como forma de crear un sistema de escritura XML de validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-105">The <xref:System.Xml.Schema.XmlSchemaValidator> class can be used in advanced scenarios such as building validation engines over custom XML data sources or as a way to build a validating XML writer.</span></span>

<span data-ttu-id="28e13-106">A continuación se ofrece un ejemplo del uso de la clase <xref:System.Xml.Schema.XmlSchemaValidator> para validar el archivo `contosoBooks.xml` con el esquema `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="28e13-106">The following is an example of using the <xref:System.Xml.Schema.XmlSchemaValidator> class to validate the `contosoBooks.xml` file against the `contosoBooks.xsd` schema.</span></span> <span data-ttu-id="28e13-107">El ejemplo utiliza la clase <xref:System.Xml.Serialization.XmlSerializer> para deserializar el archivo `contosoBooks.xml` y pasar el valor de los nodos a los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-107">The example uses the <xref:System.Xml.Serialization.XmlSerializer> class to deserialize the `contosoBooks.xml` file and pass the value of the nodes to the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

> [!NOTE]
> <span data-ttu-id="28e13-108">Este ejemplo se utiliza a lo largo de las secciones de este tema.</span><span class="sxs-lookup"><span data-stu-id="28e13-108">This example is used throughout the sections of this topic.</span></span>

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

<span data-ttu-id="28e13-109">En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.</span><span class="sxs-lookup"><span data-stu-id="28e13-109">The example takes the `contosoBooks.xml` file as input.</span></span>

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

<span data-ttu-id="28e13-110">En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.</span><span class="sxs-lookup"><span data-stu-id="28e13-110">The example also takes the `contosoBooks.xsd` as an input.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a><span data-ttu-id="28e13-111">Validación de datos XML con XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="28e13-111">Validating XML Data using XmlSchemaValidator</span></span>

<span data-ttu-id="28e13-112">Para comenzar la validación de un conjunto de información XML, primero se debe inicializar una instancia nueva de la clase <xref:System.Xml.Schema.XmlSchemaValidator> utilizando el constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-112">To begin validating an XML infoset, you must first initialize a new instance of the <xref:System.Xml.Schema.XmlSchemaValidator> class using the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor.</span></span>

<span data-ttu-id="28e13-113">El constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> toma los objetos <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> y <xref:System.Xml.XmlNamespaceManager> como parámetros, así como un valor <xref:System.Xml.Schema.XmlSchemaValidationFlags> como parámetro.</span><span class="sxs-lookup"><span data-stu-id="28e13-113">The <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor takes <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet>, and <xref:System.Xml.XmlNamespaceManager> objects as parameters as well as a <xref:System.Xml.Schema.XmlSchemaValidationFlags> value as a parameter.</span></span> <span data-ttu-id="28e13-114">El objeto <xref:System.Xml.XmlNameTable> se utiliza para atomizar cadenas de espacios de nombres bien conocidas (como el espacio de nombres del esquema, el espacio de nombres XML, etc.), y se pasa al método <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> mientras se valida contenido simple.</span><span class="sxs-lookup"><span data-stu-id="28e13-114">The <xref:System.Xml.XmlNameTable> object is used to atomize well-known namespace strings like the schema namespace, the XML namespace, and so on, and is passed to the <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> method while validating simple content.</span></span> <span data-ttu-id="28e13-115">El objeto <xref:System.Xml.Schema.XmlSchemaSet> contiene los esquemas XML que se utilizan para validar el conjunto de información XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-115">The <xref:System.Xml.Schema.XmlSchemaSet> object contains the XML schemas used to validate the XML infoset.</span></span> <span data-ttu-id="28e13-116">El objeto <xref:System.Xml.XmlNamespaceManager> se utiliza para resolver espacios de nombres que se encuentran durante la validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-116">The <xref:System.Xml.XmlNamespaceManager> object is used to resolve namespaces encountered during validation.</span></span> <span data-ttu-id="28e13-117">El valor <xref:System.Xml.Schema.XmlSchemaValidationFlags> se utiliza para deshabilitar determinadas características de la validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-117">The <xref:System.Xml.Schema.XmlSchemaValidationFlags> value is used to disable certain features of validation.</span></span>

<span data-ttu-id="28e13-118">Para obtener más información sobre el constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-118">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="initializing-validation"></a><span data-ttu-id="28e13-119">Inicialización de la validación</span><span class="sxs-lookup"><span data-stu-id="28e13-119">Initializing Validation</span></span>

<span data-ttu-id="28e13-120">Una vez construido un objeto <xref:System.Xml.Schema.XmlSchemaValidator>, existen dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> sobrecargados que se utilizan para inicializar el estado del objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-120">After an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed, there are two overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods used to initialize the state of the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="28e13-121">Éstos son los dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-121">The following are the two <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

<span data-ttu-id="28e13-122">El método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> predeterminado inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial y el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> sobrecargado, que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro, inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial para realizar una validación parcial.</span><span class="sxs-lookup"><span data-stu-id="28e13-122">The default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state, and the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="28e13-123">Los dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> solo se pueden llamar inmediatamente después de construir un objeto <xref:System.Xml.Schema.XmlSchemaValidator> o después de una llamada a <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-123">Both <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> methods can only be called immediately after an <xref:System.Xml.Schema.XmlSchemaValidator> object has been constructed or after a call to <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.</span></span>

<span data-ttu-id="28e13-124">Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-124">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method, see the example in the introduction.</span></span> <span data-ttu-id="28e13-125">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-125">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="partial-validation"></a><span data-ttu-id="28e13-126">Validación parcial</span><span class="sxs-lookup"><span data-stu-id="28e13-126">Partial Validation</span></span>

<span data-ttu-id="28e13-127">El método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> que toma un objeto <xref:System.Xml.Schema.XmlSchemaObject> como parámetro inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial para realizar una validación parcial.</span><span class="sxs-lookup"><span data-stu-id="28e13-127">The <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter initializes an <xref:System.Xml.Schema.XmlSchemaValidator> object to its starting state for partial validation.</span></span>

<span data-ttu-id="28e13-128">En el siguiente ejemplo, se inicializa un <xref:System.Xml.Schema.XmlSchemaObject> para realizar una validación parcial utilizando el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="28e13-128">In the following example, an <xref:System.Xml.Schema.XmlSchemaObject> is initialized for partial validation using the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="28e13-129">Para pasar el elemento de esquema `orderNumber`, se selecciona por <xref:System.Xml.XmlQualifiedName> en la colección <xref:System.Xml.Schema.XmlSchemaObjectTable> que devuelve la propiedad <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> del objeto <xref:System.Xml.Schema.XmlSchemaSet>.</span><span class="sxs-lookup"><span data-stu-id="28e13-129">The `orderNumber` schema element is passed by selecting the schema element by <xref:System.Xml.XmlQualifiedName> in the <xref:System.Xml.Schema.XmlSchemaObjectTable> collection returned by the <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> property of the <xref:System.Xml.Schema.XmlSchemaSet> object.</span></span> <span data-ttu-id="28e13-130">A continuación, el objeto <xref:System.Xml.Schema.XmlSchemaValidator> valida este elemento específico.</span><span class="sxs-lookup"><span data-stu-id="28e13-130">The <xref:System.Xml.Schema.XmlSchemaValidator> object then validates this specific element.</span></span>

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

<span data-ttu-id="28e13-131">En el ejemplo, se toma como entrada el siguiente esquema XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-131">The example takes the following XML schema as input.</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

<span data-ttu-id="28e13-132">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-132">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="adding-additional-schemas"></a><span data-ttu-id="28e13-133">Adición de esquemas adicionales</span><span class="sxs-lookup"><span data-stu-id="28e13-133">Adding Additional Schemas</span></span>

<span data-ttu-id="28e13-134">El método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> se utiliza para agregar un esquema XML al conjunto de esquemas que se utiliza durante la validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-134">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method of the <xref:System.Xml.Schema.XmlSchemaValidator> class is used to add an XML schema to the set of schemas used during validation.</span></span> <span data-ttu-id="28e13-135">El método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> se puede utilizar para simular el efecto de encontrarse un esquema XML alineado en el conjunto de información XML que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-135">The <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method can be used to simulate the effect of encountering an inline XML schema in the XML infoset being validated.</span></span>

> [!NOTE]
> <span data-ttu-id="28e13-136">El espacio de nombres de destino del parámetro <xref:System.Xml.Schema.XmlSchema> no puede coincidir con el de ningún elemento o atributo que ya haya encontrado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-136">The target namespace of the <xref:System.Xml.Schema.XmlSchema> parameter cannot match that of any element or attribute already encountered by the <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>
>
> <span data-ttu-id="28e13-137">Si el valor <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> no se hubiera pasado como parámetro al constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, el método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> no haría nada.</span><span class="sxs-lookup"><span data-stu-id="28e13-137">If the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> value was not passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> constructor, the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method does nothing.</span></span>

<span data-ttu-id="28e13-138">El resultado del método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> depende del contexto del nodo XML actual que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-138">The result of the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method is dependant on the current XML node context being validated.</span></span> <span data-ttu-id="28e13-139">Para obtener más información sobre los contextos de validación, vea la sección "Contexto de validación" en este tema.</span><span class="sxs-lookup"><span data-stu-id="28e13-139">For more information about validation contexts, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="28e13-140">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-140">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="validating-elements-attributes-and-content"></a><span data-ttu-id="28e13-141">Validación de elementos, atributos y contenido</span><span class="sxs-lookup"><span data-stu-id="28e13-141">Validating Elements, Attributes, and Content</span></span>

<span data-ttu-id="28e13-142">La clase <xref:System.Xml.Schema.XmlSchemaValidator> incluye varios métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML con esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-142">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides several methods used to validate elements, attributes, and content in an XML infoset against XML schemas.</span></span> <span data-ttu-id="28e13-143">En la siguiente tabla se describen cada uno de estos métodos.</span><span class="sxs-lookup"><span data-stu-id="28e13-143">The following table describes each of these methods.</span></span>

|<span data-ttu-id="28e13-144">Método</span><span class="sxs-lookup"><span data-stu-id="28e13-144">Method</span></span>|<span data-ttu-id="28e13-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="28e13-145">Description</span></span>|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="28e13-146">Valida el nombre del elemento en el contexto actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-146">Validates the element name in the current context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="28e13-147">Valida el atributo en el contexto del elemento actual o con el objeto <xref:System.Xml.Schema.XmlSchemaAttribute> que se pasa como parámetro al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-147">Validates the attribute in the current element context or against the <xref:System.Xml.Schema.XmlSchemaAttribute> object passed as a parameter to the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="28e13-148">Comprueba si todos los atributos requeridos del contexto del elemento están presentes y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar el contenido secundario del elemento.</span><span class="sxs-lookup"><span data-stu-id="28e13-148">Verifies whether all the required attributes in the element context are present and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate the child content of the element.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="28e13-149">Valida si se permite texto en el contexto del elemento actual y acumula el texto para validar si el elemento actual tiene contenido simple.</span><span class="sxs-lookup"><span data-stu-id="28e13-149">Validates whether text is allowed in the current element context, and accumulates the text for validation if the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="28e13-150">Valida si se permite espacio en blanco en el contexto del elemento actual y acumula el espacio en blanco para validar si el elemento actual tiene contenido simple.</span><span class="sxs-lookup"><span data-stu-id="28e13-150">Validates whether white-space is allowed in the current element context, and accumulates the white-space for validation whether the current element has simple content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="28e13-151">Comprueba si el contenido de texto del elemento es válido de acuerdo con su tipo de datos para elementos con contenido simple, y comprueba si el contenido del elemento actual está completo para los elementos con contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="28e13-151">Verifies whether the text content of the element is valid according to its data type for elements with simple content, and verifies whether the content of the current element is complete for elements with complex content.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="28e13-152">Omite la validación del contenido del elemento actual y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar contenido en el contexto del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="28e13-152">Skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="28e13-153">Termina la validación y comprueba las restricciones de identidad de todo el documento XML si se establece la opción de validación <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.</span><span class="sxs-lookup"><span data-stu-id="28e13-153">Ends validation and checks identity constraints for the entire XML document if the <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints> validation option is set.</span></span>|

> [!NOTE]
> <span data-ttu-id="28e13-154">La clase <xref:System.Xml.Schema.XmlSchemaValidator> tiene una transición de estado definida que exige la secuencia y ocurrencia de las llamadas realizadas a cada uno de los métodos que se describen en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="28e13-154">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods described in the previous table.</span></span> <span data-ttu-id="28e13-155">La transición de estado específica de la clase <xref:System.Xml.Schema.XmlSchemaValidator> se describe en la sección "Transición de estado de XmlSchemaValidator" de este tema.</span><span class="sxs-lookup"><span data-stu-id="28e13-155">The specific state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class is described in the "XmlSchemaValidator State Transition" section of this topic.</span></span>

<span data-ttu-id="28e13-156">Para obtener un ejemplo de los métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML, vea el ejemplo de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="28e13-156">For an example of the methods used to validate elements, attributes, and content in an XML infoset, see the example in the previous section.</span></span> <span data-ttu-id="28e13-157">Para obtener más información sobre estos métodos, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-157">For more information about these methods, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="validating-content-using-an-xmlvaluegetter"></a><span data-ttu-id="28e13-158">Validación de contenido con XmlValueGetter</span><span class="sxs-lookup"><span data-stu-id="28e13-158">Validating Content Using an XmlValueGetter</span></span>

<span data-ttu-id="28e13-159"><xref:System.Xml.Schema.XmlValueGetter>`delegate` se puede utilizar para pasar el valor de los nodos de atributos, textos o espacios en blanco como tipos Common Language Runtime (CLR) compatibles con el tipo del lenguaje de definición de esquema XML (XSD) del nodo de atributos, textos o espacios en blanco.</span><span class="sxs-lookup"><span data-stu-id="28e13-159">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` can be used to pass the value of attribute, text, or white-space nodes as a Common Language Runtime (CLR) types compatible with the XML Schema Definition Language (XSD) type of the attribute, text, or white-space node.</span></span> <span data-ttu-id="28e13-160"><xref:System.Xml.Schema.XmlValueGetter>`delegate` es útil si el valor CLR de un nodo de atributos, textos o espacios en blanco ya está disponible y evita el costo de convertirlo en un valor `string` y luego volver a analizarlo para validarlo.</span><span class="sxs-lookup"><span data-stu-id="28e13-160">An <xref:System.Xml.Schema.XmlValueGetter>`delegate` is useful if the CLR value of an attribute, text, or white-space node is already available, and avoids the cost of converting it to a `string` and then reparsing it again for validation.</span></span>

<span data-ttu-id="28e13-161">Los métodos <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> están sobrecargados y aceptan el valor de los nodos de atributos, textos o espacios en blanco como un `string` o <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span><span class="sxs-lookup"><span data-stu-id="28e13-161">The <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> methods are overloaded and accept the value of attribute, text, or white-space nodes as a `string` or <xref:System.Xml.Schema.XmlValueGetter>`delegate`.</span></span>

<span data-ttu-id="28e13-162">Los siguientes métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> aceptan un <xref:System.Xml.Schema.XmlValueGetter>`delegate` como parámetro.</span><span class="sxs-lookup"><span data-stu-id="28e13-162">The following methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlValueGetter>`delegate` as a parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

<span data-ttu-id="28e13-163">A continuación, se ofrece un ejemplo de un <xref:System.Xml.Schema.XmlValueGetter>`delegate` tomado del ejemplo de la clase <xref:System.Xml.Schema.XmlSchemaValidator> de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-163">The following is an example <xref:System.Xml.Schema.XmlValueGetter>`delegate` taken from the <xref:System.Xml.Schema.XmlSchemaValidator> class example in the introduction.</span></span> <span data-ttu-id="28e13-164"><xref:System.Xml.Schema.XmlValueGetter>`delegate` devuelve el valor de un atributo como un objeto <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="28e13-164">The <xref:System.Xml.Schema.XmlValueGetter>`delegate` returns the value of an attribute as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="28e13-165">Para validar este objeto <xref:System.DateTime> que devuelve <xref:System.Xml.Schema.XmlValueGetter>, el objeto <xref:System.Xml.Schema.XmlSchemaValidator> primero lo convierte en ValueType (ValueType es la asignación CLR predeterminada para el tipo XSD) para el tipo de datos del atributo y, a continuación, comprueba las facetas en el valor convertido.</span><span class="sxs-lookup"><span data-stu-id="28e13-165">To validate this <xref:System.DateTime> object returned by the <xref:System.Xml.Schema.XmlValueGetter>, the <xref:System.Xml.Schema.XmlSchemaValidator> object first converts it to the ValueType (ValueType is the default CLR mapping for the XSD type) for the data type of the attribute and then checks facets on the converted value.</span></span>

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

<span data-ttu-id="28e13-166">Para obtener un ejemplo completo de <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-166">For a complete example of the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the example in the introduction.</span></span> <span data-ttu-id="28e13-167">Para obtener más información sobre <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vea la documentación de referencia de las clases <xref:System.Xml.Schema.XmlValueGetter> y <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-167">For more information about the <xref:System.Xml.Schema.XmlValueGetter>`delegate`, see the <xref:System.Xml.Schema.XmlValueGetter>, and <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="post-schema-validation-information"></a><span data-ttu-id="28e13-168">Información posterior a la validación del esquema</span><span class="sxs-lookup"><span data-stu-id="28e13-168">Post-Schema-Validation-Information</span></span>

<span data-ttu-id="28e13-169">La clase <xref:System.Xml.Schema.XmlSchemaInfo> representa parte de la información posterior a la validación del esquema de un nodo XML que valida la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-169">The <xref:System.Xml.Schema.XmlSchemaInfo> class represents some of the Post-Schema-Validation-Information of an XML node validated by the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="28e13-170">Hay varios métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que aceptan un objeto <xref:System.Xml.Schema.XmlSchemaInfo> como un parámetro `null` opcional (`out`).</span><span class="sxs-lookup"><span data-stu-id="28e13-170">Various methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an optional, (`null`) `out` parameter.</span></span>

<span data-ttu-id="28e13-171">Después de realizar la validación correctamente, se establecen las propiedades del objeto <xref:System.Xml.Schema.XmlSchemaInfo> con los resultados de la validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-171">Upon successful validation, properties of the <xref:System.Xml.Schema.XmlSchemaInfo> object are set with the results of the validation.</span></span> <span data-ttu-id="28e13-172">Por ejemplo, después de validar correctamente un atributo utilizando el método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, las propiedades <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> y <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> del objeto <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> se establecen con los resultados de la validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-172">For example, upon successful validation of an attribute using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the <xref:System.Xml.Schema.XmlSchemaInfo> object's (if specified) <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A>, and <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> properties are set with the results of the validation.</span></span>

<span data-ttu-id="28e13-173">Los siguientes métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> aceptan un objeto <xref:System.Xml.Schema.XmlSchemaInfo> como parámetro out.</span><span class="sxs-lookup"><span data-stu-id="28e13-173">The following <xref:System.Xml.Schema.XmlSchemaValidator> class methods accept an <xref:System.Xml.Schema.XmlSchemaInfo> object as an out parameter.</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

<span data-ttu-id="28e13-174">Para obtener un ejemplo completo de la clase <xref:System.Xml.Schema.XmlSchemaInfo>, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-174">For a complete example of the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the example in the introduction.</span></span> <span data-ttu-id="28e13-175">Para obtener más información sobre la clase <xref:System.Xml.Schema.XmlSchemaInfo>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="28e13-175">For more information about the <xref:System.Xml.Schema.XmlSchemaInfo> class, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a><span data-ttu-id="28e13-176">Recuperación de partículas y atributos esperados y atributos predeterminados no especificados</span><span class="sxs-lookup"><span data-stu-id="28e13-176">Retrieving Expected Particles, Attributes, and Unspecified Default Attributes</span></span>

<span data-ttu-id="28e13-177">La clase <xref:System.Xml.Schema.XmlSchemaValidator> proporciona los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> para recuperar las partículas y atributos esperados y los atributos predeterminados no especificados en el contexto de validación actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-177">The <xref:System.Xml.Schema.XmlSchemaValidator> class provides the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> methods to retrieve the expected particles, attributes, and unspecified default attributes in the current validation context.</span></span>

#### <a name="retrieving-expected-particles"></a><span data-ttu-id="28e13-178">Recuperación de partículas esperadas</span><span class="sxs-lookup"><span data-stu-id="28e13-178">Retrieving Expected Particles</span></span>

<span data-ttu-id="28e13-179">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz de objetos <xref:System.Xml.Schema.XmlSchemaParticle> que contienen las partículas esperadas en el contexto del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-179">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaParticle> objects containing the expected particles in the current element context.</span></span> <span data-ttu-id="28e13-180">Las partículas válidas que puede devolver el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> son instancias de las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAny>.</span><span class="sxs-lookup"><span data-stu-id="28e13-180">The valid particles that can be returned by the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method are instances of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAny> classes.</span></span>

<span data-ttu-id="28e13-181">Cuando el compositor del modelo de contenido es `xs:sequence`, solo se devuelve la siguiente partícula de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="28e13-181">When the compositor for the content model is an `xs:sequence`, only the next particle in the sequence is returned.</span></span> <span data-ttu-id="28e13-182">Si el compositor del modelo de contenido es `xs:all` o `xs:choice`, se devuelven todas las partículas válidas que pueden ir a continuación en el contexto del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-182">If the compositor for the content model is an `xs:all` or an `xs:choice`, then all valid particles that could follow in the current element context are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="28e13-183">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> inmediatamente después de llamar al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve todos los elementos globales.</span><span class="sxs-lookup"><span data-stu-id="28e13-183">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called immediately after calling the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns all global elements.</span></span>

<span data-ttu-id="28e13-184">Por ejemplo, en el esquema del lenguaje de definición de esquemas XML (XSD) y en el documento XML que sigue, después de validar el elemento `book`, el elemento `book` es el contexto del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-184">For example, in the XML Schema Definition Language (XSD) schema and XML document that follow, after validating the `book` element, the `book` element is the current element context.</span></span> <span data-ttu-id="28e13-185">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaElement> que representa el elemento `title`.</span><span class="sxs-lookup"><span data-stu-id="28e13-185">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `title` element.</span></span> <span data-ttu-id="28e13-186">Cuando el contexto de validación es el elemento `title`, el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-186">When the validation context is the `title` element, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method returns an empty array.</span></span> <span data-ttu-id="28e13-187">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> después de que se haya validado el elemento `title`, pero antes de validar el elemento `description`, devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaElement> que representa el elemento `description`.</span><span class="sxs-lookup"><span data-stu-id="28e13-187">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `title` element has been validated but before the `description` element has been validated, it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaElement> object representing the `description` element.</span></span> <span data-ttu-id="28e13-188">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> después de que se haya validado el elemento `description`, devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaAny> que representa el comodín.</span><span class="sxs-lookup"><span data-stu-id="28e13-188">If the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method is called after the `description` element has been validated then it returns an array containing a single <xref:System.Xml.Schema.XmlSchemaAny> object representing the wildcard.</span></span>

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 <span data-ttu-id="28e13-189">En el ejemplo se toma como entrada el siguiente XML:</span><span class="sxs-lookup"><span data-stu-id="28e13-189">The example takes the following XML as input:</span></span>

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

<span data-ttu-id="28e13-190">En el ejemplo se toma como entrada el siguiente esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="28e13-190">The example takes the following XSD schema as input:</span></span>

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> <span data-ttu-id="28e13-191">Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-191">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="28e13-192">Para obtener más información, vea la sección "Contexto de validación" de este tema.</span><span class="sxs-lookup"><span data-stu-id="28e13-192">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="28e13-193">Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-193">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="28e13-194">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-194">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-expected-attributes"></a><span data-ttu-id="28e13-195">Recuperación de atributos esperados</span><span class="sxs-lookup"><span data-stu-id="28e13-195">Retrieving Expected Attributes</span></span>

<span data-ttu-id="28e13-196">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz de objetos <xref:System.Xml.Schema.XmlSchemaAttribute> que contienen los atributos esperados en el contexto del elemento actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-196">The <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method returns an array of <xref:System.Xml.Schema.XmlSchemaAttribute> objects containing the expected attributes in the current element context.</span></span>

<span data-ttu-id="28e13-197">Por ejemplo, en el ejemplo de la introducción, se utiliza el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> para recuperar todos los atributos del elemento `book`.</span><span class="sxs-lookup"><span data-stu-id="28e13-197">For example, in the example in the introduction, the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method is used to retrieve all the attributes of the `book` element.</span></span>

<span data-ttu-id="28e13-198">Si llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> inmediatamente después del método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, se devuelven todos los atributos que podrían aparecer en el documento XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-198">If you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method immediately after the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> method, all the attributes that could appear in the XML document are returned.</span></span> <span data-ttu-id="28e13-199">Sin embargo, si llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> después de una o más llamadas al método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, se devuelven los atributos que aún no se han validado para el elemento actual.</span><span class="sxs-lookup"><span data-stu-id="28e13-199">However, if you call the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method after one or more calls to the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method, the attributes that have not yet been validated for the current element are returned.</span></span>

> [!NOTE]
> <span data-ttu-id="28e13-200">Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-200">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span> <span data-ttu-id="28e13-201">Para obtener más información, vea la sección "Contexto de validación" de este tema.</span><span class="sxs-lookup"><span data-stu-id="28e13-201">For more information, see the "Validation Context" section of this topic.</span></span>

<span data-ttu-id="28e13-202">Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-202">For an example of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the example in the introduction.</span></span> <span data-ttu-id="28e13-203">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-203">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

#### <a name="retrieving-unspecified-default-attributes"></a><span data-ttu-id="28e13-204">Recuperación de atributos predeterminados no especificados</span><span class="sxs-lookup"><span data-stu-id="28e13-204">Retrieving Unspecified Default Attributes</span></span>

<span data-ttu-id="28e13-205">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> rellena el <xref:System.Collections.ArrayList> especificado con objetos <xref:System.Xml.Schema.XmlSchemaAttribute> para cualquier atributo con valores predeterminados que no haya sido validado previamente con el método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> en el contexto del elemento.</span><span class="sxs-lookup"><span data-stu-id="28e13-205">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method populates the <xref:System.Collections.ArrayList> specified with <xref:System.Xml.Schema.XmlSchemaAttribute> objects for any attributes with default values that have not been previously validated using the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method in the element context.</span></span> <span data-ttu-id="28e13-206">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> se debería llamar después de llamar al método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> en cada atributo del contexto del elemento.</span><span class="sxs-lookup"><span data-stu-id="28e13-206">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be called after calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> method on each attribute in the element context.</span></span> <span data-ttu-id="28e13-207">El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> se debería utilizar para determinar qué atributos predeterminados se van a insertar en el documento XML que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-207">The <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method should be used to determine what default attributes are to be inserted into the XML document being validated.</span></span>

<span data-ttu-id="28e13-208">Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-208">For more information about the <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> method, see the <xref:System.Xml.Schema.XmlSchemaValidator> class reference documentation.</span></span>

### <a name="handling-schema-validation-events"></a><span data-ttu-id="28e13-209">Control de eventos de validación de esquemas</span><span class="sxs-lookup"><span data-stu-id="28e13-209">Handling Schema Validation Events</span></span>

<span data-ttu-id="28e13-210">Las advertencias y errores de validación de esquemas que se encuentran durante la validación se controlan por medio del evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-210">Schema validation warnings and errors encountered during validation are handled by the <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> event of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

<span data-ttu-id="28e13-211">Las advertencias de validación de esquemas tienen un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Warning> y los errores de validación de esquemas tienen un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="28e13-211">Schema validation warnings have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning> and schema validation errors have an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="28e13-212">Si no se ha asignado ningún <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>, se inicia una <xref:System.Xml.Schema.XmlSchemaValidationException> para todos los errores de validación de esquemas con un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Error>.</span><span class="sxs-lookup"><span data-stu-id="28e13-212">If no <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> has been assigned, an <xref:System.Xml.Schema.XmlSchemaValidationException> is thrown for all schema validation errors with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Error>.</span></span> <span data-ttu-id="28e13-213">Sin embargo, no se inicia una <xref:System.Xml.Schema.XmlSchemaValidationException> para las advertencias de validación de esquemas con un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span><span class="sxs-lookup"><span data-stu-id="28e13-213">However, an <xref:System.Xml.Schema.XmlSchemaValidationException> is not thrown for schema validation warnings with an <xref:System.Xml.Schema.XmlSeverityType> value of <xref:System.Xml.Schema.XmlSeverityType.Warning>.</span></span>

<span data-ttu-id="28e13-214">A continuación, se ofrece un ejemplo de un <xref:System.Xml.Schema.ValidationEventHandler> que recibe errores y advertencias de validación de esquemas que se encuentran durante la validación de esquemas tomada del ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-214">The following is an example of a <xref:System.Xml.Schema.ValidationEventHandler> that receives schema validation warnings and errors encountered during schema validation taken from the example in the introduction.</span></span>

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

<span data-ttu-id="28e13-215">Para obtener un ejemplo completo de <xref:System.Xml.Schema.ValidationEventHandler>, vea el ejemplo de la introducción.</span><span class="sxs-lookup"><span data-stu-id="28e13-215">For a complete example of the <xref:System.Xml.Schema.ValidationEventHandler>, see the example in the introduction.</span></span> <span data-ttu-id="28e13-216">Para obtener más información, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaInfo>.</span><span class="sxs-lookup"><span data-stu-id="28e13-216">For more information, see the <xref:System.Xml.Schema.XmlSchemaInfo> class reference documentation.</span></span>

## <a name="xmlschemavalidator-state-transition"></a><span data-ttu-id="28e13-217">Transición de estado de XmlSchemaValidator</span><span class="sxs-lookup"><span data-stu-id="28e13-217">XmlSchemaValidator State Transition</span></span>

<span data-ttu-id="28e13-218">La clase <xref:System.Xml.Schema.XmlSchemaValidator> tiene una transición de estado definida que exige la secuencia y ocurrencia de las llamadas realizadas a cada uno de los métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-218">The <xref:System.Xml.Schema.XmlSchemaValidator> class has a defined state transition that enforces the sequence and occurrence of calls made to each of the methods used to validate elements, attributes, and content in an XML infoset.</span></span>

<span data-ttu-id="28e13-219">En la siguiente tabla se describe la transición de estado de la clase <xref:System.Xml.Schema.XmlSchemaValidator> y la secuencia y ocurrencia de las llamadas de método que se pueden realizar en cada estado.</span><span class="sxs-lookup"><span data-stu-id="28e13-219">The following table describes the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class, and the sequence and occurrence of method calls that can be made in each state.</span></span>

|<span data-ttu-id="28e13-220">Estado</span><span class="sxs-lookup"><span data-stu-id="28e13-220">State</span></span>|<span data-ttu-id="28e13-221">Transición</span><span class="sxs-lookup"><span data-stu-id="28e13-221">Transition</span></span>|
|-----------|----------------|
|<span data-ttu-id="28e13-222">Validar</span><span class="sxs-lookup"><span data-stu-id="28e13-222">Validate</span></span>|<span data-ttu-id="28e13-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span><span class="sxs-lookup"><span data-stu-id="28e13-223"><xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel\*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A></span></span>|
|<span data-ttu-id="28e13-224">TopLevel</span><span class="sxs-lookup"><span data-stu-id="28e13-224">TopLevel</span></span>|<span data-ttu-id="28e13-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="28e13-225"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|
|<span data-ttu-id="28e13-226">Elemento</span><span class="sxs-lookup"><span data-stu-id="28e13-226">Element</span></span>|<span data-ttu-id="28e13-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span><span class="sxs-lookup"><span data-stu-id="28e13-227"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\*)?</span></span> <span data-ttu-id="28e13-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="28e13-228"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="28e13-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="28e13-229"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span><br /><br /> <span data-ttu-id="28e13-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span><span class="sxs-lookup"><span data-stu-id="28e13-230"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> Content\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> &#124;</span></span>|
|<span data-ttu-id="28e13-231">Contenido</span><span class="sxs-lookup"><span data-stu-id="28e13-231">Content</span></span>|<span data-ttu-id="28e13-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span><span class="sxs-lookup"><span data-stu-id="28e13-232"><xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element</span></span>|

> [!NOTE]
> <span data-ttu-id="28e13-233">Cada uno de los métodos de la tabla anterior inicia una <xref:System.InvalidOperationException> cuando se realiza la llamada al método en la secuencia incorrecta de acuerdo con el estado actual de un objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-233">An <xref:System.InvalidOperationException> is thrown by each of the methods in the table above when the call to the method is made in the incorrect sequence according to the current state of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span>

<span data-ttu-id="28e13-234">La tabla de transición de estado anterior utiliza signos de puntuación para describir los métodos y otros estados que se pueden llamar para cada estado de la transición de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-234">The state transition table above uses punctuation symbols to describe the methods and other states that can be called for each state of the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span> <span data-ttu-id="28e13-235">Los signos que se utilizan son los mismos que se encuentran en la referencia de estándares XML de la definición de tipos de documento (DTD).</span><span class="sxs-lookup"><span data-stu-id="28e13-235">The symbols used are the same symbols found in the XML Standards reference for Document Type Definition (DTD).</span></span>

<span data-ttu-id="28e13-236">En la siguiente tabla se describe cómo los signos de puntuación que se encuentran en la tabla de transiciones de estado anterior afectan a los métodos y otros estados que se pueden llamar para cada estado de la transición de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-236">The following table describes how the punctuation symbols found in the state transition table above affect the methods and other states that can be called for each state in the state transition of the <xref:System.Xml.Schema.XmlSchemaValidator> class.</span></span>

|<span data-ttu-id="28e13-237">Símbolo</span><span class="sxs-lookup"><span data-stu-id="28e13-237">Symbol</span></span>|<span data-ttu-id="28e13-238">Descripción</span><span class="sxs-lookup"><span data-stu-id="28e13-238">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="28e13-239">&#124;</span><span class="sxs-lookup"><span data-stu-id="28e13-239">&#124;</span></span>|<span data-ttu-id="28e13-240">Se puede llamar al método o al estado (al que está antes o después de la barra).</span><span class="sxs-lookup"><span data-stu-id="28e13-240">Either method or state (the one before the bar or the one after it) can be called.</span></span>|
|<span data-ttu-id="28e13-241">?</span><span class="sxs-lookup"><span data-stu-id="28e13-241">?</span></span>|<span data-ttu-id="28e13-242">El método o estado que precede al signo de interrogación es opcional, pero si se llama, solo se puede llamar una vez.</span><span class="sxs-lookup"><span data-stu-id="28e13-242">The method or state that precedes the question mark is optional but if it is called it can only be called once.</span></span>|
|*|<span data-ttu-id="28e13-243">El método o estado que precede al símbolo \* es opcional y se puede llamar más de una vez.</span><span class="sxs-lookup"><span data-stu-id="28e13-243">The method or state that precedes the \* symbol is optional, and can be called more than once.</span></span>|

## <a name="validation-context"></a><span data-ttu-id="28e13-244">Contexto de validación</span><span class="sxs-lookup"><span data-stu-id="28e13-244">Validation Context</span></span>

<span data-ttu-id="28e13-245">Los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML cambian el contexto de validación de un objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-245">The methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset, change the validation context of an <xref:System.Xml.Schema.XmlSchemaValidator> object.</span></span> <span data-ttu-id="28e13-246">Por ejemplo, el método <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> omite la validación del contenido del elemento actual y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar contenido en el contexto del elemento primario; es equivalente a la omisión de la validación para todos los elementos secundarios del elemento actual y luego a la llamada del método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-246">For example, the <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> method skips validation of the current element content and prepares the <xref:System.Xml.Schema.XmlSchemaValidator> object to validate content in the parent element's context; it is equivalent to skipping validation for all the children of the current element and then calling the <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> method.</span></span>

<span data-ttu-id="28e13-247">Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando.</span><span class="sxs-lookup"><span data-stu-id="28e13-247">The results of the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, and <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class are dependent on the current context being validated.</span></span>

<span data-ttu-id="28e13-248">En la siguiente tabla se describen los resultados de las llamadas a estos métodos después de llamar a uno de los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que se utiliza para validar elementos, atributos y contenido en un conjunto de información XML.</span><span class="sxs-lookup"><span data-stu-id="28e13-248">The following table describes the results of calling these methods after calling one of the methods of the <xref:System.Xml.Schema.XmlSchemaValidator> class used to validate elements, attributes, and content in an XML infoset.</span></span>

|<span data-ttu-id="28e13-249">Método</span><span class="sxs-lookup"><span data-stu-id="28e13-249">Method</span></span>|<span data-ttu-id="28e13-250">GetExpectedParticles</span><span class="sxs-lookup"><span data-stu-id="28e13-250">GetExpectedParticles</span></span>|<span data-ttu-id="28e13-251">GetExpectedAttributes</span><span class="sxs-lookup"><span data-stu-id="28e13-251">GetExpectedAttributes</span></span>|<span data-ttu-id="28e13-252">AddSchema</span><span class="sxs-lookup"><span data-stu-id="28e13-252">AddSchema</span></span>|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|<span data-ttu-id="28e13-253">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> predeterminado, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz que contiene todos los elementos globales.</span><span class="sxs-lookup"><span data-stu-id="28e13-253">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an array containing all global elements.</span></span><br /><br /> <span data-ttu-id="28e13-254">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> sobrecargado que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro para inicializar la validación parcial de un elemento, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve solo el elemento en el cual se ha inicializado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-254">If the overloaded <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an element, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns only the element to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="28e13-255">Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> predeterminado, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-255">If the default <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method is called, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-256">Si se llama a la sobrecarga del método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro para inicializar la validación parcial de un atributo, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve solo el atributo en el cual se ha inicializado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.</span><span class="sxs-lookup"><span data-stu-id="28e13-256">If the overload of the <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> method that takes an <xref:System.Xml.Schema.XmlSchemaObject> as a parameter is called to initialize partial validation of an attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns only the attribute to which the <xref:System.Xml.Schema.XmlSchemaValidator> object was initialized.</span></span>|<span data-ttu-id="28e13-257">Agrega el esquema al <xref:System.Xml.Schema.XmlSchemaSet> del objeto <xref:System.Xml.Schema.XmlSchemaValidator> si no tiene errores de procesamiento previo.</span><span class="sxs-lookup"><span data-stu-id="28e13-257">Adds the schema to the <xref:System.Xml.Schema.XmlSchemaSet> of the <xref:System.Xml.Schema.XmlSchemaValidator> object if it has no preprocessing errors.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|<span data-ttu-id="28e13-258">Si el elemento del contexto es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como elementos secundarios del elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-258">If the context element is valid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as children of the context element.</span></span><br /><br /> <span data-ttu-id="28e13-259">Si el elemento del contexto no es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-259">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span>|<span data-ttu-id="28e13-260">Si el elemento del contexto es válido, y si no se ha realizado previamente ninguna llamada a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de todos los atributos definidos en el elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-260">If the context element is valid, and if no call to <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> has been previously made, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of all the attributes defined on the context element.</span></span><br /><br /> <span data-ttu-id="28e13-261">Si ya se han validado algunos atributos, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de los atributos restantes que hay que validar.</span><span class="sxs-lookup"><span data-stu-id="28e13-261">If some attributes have already been validated, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the remaining attributes to be validated.</span></span><br /><br /> <span data-ttu-id="28e13-262">Si el elemento del contexto no es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-262">If the context element is invalid, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="28e13-263">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-263">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|<span data-ttu-id="28e13-264">Si el atributo del contexto es un atributo de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-264">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-265">De lo contrario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-265">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="28e13-266">Si el atributo del contexto es un atributo de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-266">If the context attribute is a top-level attribute, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-267">De lo contrario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos restantes que hay que validar.</span><span class="sxs-lookup"><span data-stu-id="28e13-267">Otherwise <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the list of remaining attributes to be validated.</span></span>|<span data-ttu-id="28e13-268">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-268">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<span data-ttu-id="28e13-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-269"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="28e13-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de los atributos requeridos y opcionales que aún quedan por validar en el elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-270"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns a list of the required and optional attributes that are yet to be validated for the context element.</span></span>|<span data-ttu-id="28e13-271">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-271">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<span data-ttu-id="28e13-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.</span><span class="sxs-lookup"><span data-stu-id="28e13-272"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected as the first child of the context element.</span></span>|<span data-ttu-id="28e13-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-273"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span>|<span data-ttu-id="28e13-274">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-274">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|<span data-ttu-id="28e13-275">Si contentType del elemento del contexto es Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada en la siguiente posición.</span><span class="sxs-lookup"><span data-stu-id="28e13-275">If the context element's contentType is Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position.</span></span><br /><br /> <span data-ttu-id="28e13-276">Si contentType del elemento del contexto es TextOnly o Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-276">If the context element's contentType is TextOnly or Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-277">Si contentType del elemento del contexto es ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada en la siguiente posición, pero ya se ha producido un error de validación.</span><span class="sxs-lookup"><span data-stu-id="28e13-277">If the context element's contentType is ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected in the next position but a validation error has already occurred.</span></span>|<span data-ttu-id="28e13-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos del elemento del contexto no validada.</span><span class="sxs-lookup"><span data-stu-id="28e13-278"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span>|<span data-ttu-id="28e13-279">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-279">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|<span data-ttu-id="28e13-280">Si el espacio en blanco del contexto es un espacio en blanco de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-280">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-281">De lo contrario, el comportamiento del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> es el mismo que en <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-281">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="28e13-282">Si el espacio en blanco del contexto es un espacio en blanco de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-282">If the context white-space is top-level white-space, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty array.</span></span><br /><br /> <span data-ttu-id="28e13-283">De lo contrario, el comportamiento del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> es el mismo que en <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-283">Otherwise the <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> method's behavior is the same as in <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.</span></span>|<span data-ttu-id="28e13-284">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-284">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<span data-ttu-id="28e13-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada después del elemento del contexto (posibles elementos relacionados).</span><span class="sxs-lookup"><span data-stu-id="28e13-285"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> returns the sequence of elements expected after the context element (possible siblings).</span></span>|<span data-ttu-id="28e13-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos del elemento del contexto no validada.</span><span class="sxs-lookup"><span data-stu-id="28e13-286"><xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns the context element's list of attributes not validated.</span></span><br /><br /> <span data-ttu-id="28e13-287">Si el elemento del contexto no tiene elemento primario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista vacía (el elemento del contexto es el elemento primario del elemento actual en el que se ha llamado a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>).</span><span class="sxs-lookup"><span data-stu-id="28e13-287">If the context element has no parent then <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> returns an empty list (the context element is the parent of the current element on which <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> was called).</span></span>|<span data-ttu-id="28e13-288">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-288">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|<span data-ttu-id="28e13-289">Igual a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-289">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="28e13-290">Igual a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span><span class="sxs-lookup"><span data-stu-id="28e13-290">Same as <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.</span></span>|<span data-ttu-id="28e13-291">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-291">Same as above.</span></span>|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|<span data-ttu-id="28e13-292">Devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-292">Returns an empty array.</span></span>|<span data-ttu-id="28e13-293">Devuelve una matriz vacía.</span><span class="sxs-lookup"><span data-stu-id="28e13-293">Returns an empty array.</span></span>|<span data-ttu-id="28e13-294">Como anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28e13-294">Same as above.</span></span>|

> [!NOTE]
> <span data-ttu-id="28e13-295">Los valores devueltos por las diversas propiedades de la clase <xref:System.Xml.Schema.XmlSchemaValidator> no cambian al llamar a cualquiera de los métodos de la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="28e13-295">The values returned by the various properties of the <xref:System.Xml.Schema.XmlSchemaValidator> class are not altered by calling any of the methods in the above table.</span></span>

## <a name="see-also"></a><span data-ttu-id="28e13-296">Vea también</span><span class="sxs-lookup"><span data-stu-id="28e13-296">See also</span></span>

- <xref:System.Xml.Schema.XmlSchemaValidator>
