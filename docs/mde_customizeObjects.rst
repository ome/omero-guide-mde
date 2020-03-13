Add custom objects to OMERO.mde
================================
**Description**
------------------
By using OMERO.mde you can create standardized key-value input forms with certain values and units. You can group key-values by creating an object module with the key-values as properties. We will show in this section how to create new objects for OMERO.mde and how you could create new key-values as properties of objects.

**Step-by-Step**
------------------
#. Open the mdeConfiguration.xml file under *<userHome>/omero/*

#. Insert a new ``<ObjectDef>`` element under ``<Definitions>`` and specify the name for the object (here MyCustomObject)::

            <MDEObjects>
                <Definitions>
                    <ObjectDef Type="MyCustomObject"/>
                </Definitions>
                <Configurations.../>
            </MDEObjects>

#. Define now the properties (key-values) for your new object. For every property you have to add an ``<TagData>`` element. See below section Type of input fields.
   
#. Define now in which hierarchy the object should be insert. For that define the parent element::
        
            <MDEObjects>
                <Definitions>
                    <ObjectDef Type="MyCustomObject">
                        <TagData.../>
                        ...
                        <Parents.../>
                    </ObjectDef>
                </Definitions>
                <Configurations.../>
            </MDEObjects>
       

Example
^^^^^^^^^^^^
Specification like::

                <MDEConfiguration>
                    <MDEPredefinitions...>
                    <MDEObjects>
                        <Definitions>
                            ...
                            <ObjectDef Type="MyCustomObject">
                                <TagData DefaultValues="" Name="ExampleKey_1" Type="TextField"
                                            Unit="" Value="" Visible="true" />
                                <TagData DefaultValues="" Name="ExampleKey_2" Type="TextField"
                                            Unit="" Value="" Visible="true" />
                                <Parents Values="OME:Image" />
                            </ObjectDef>
                        </Definitions>
                        <Configuration.../>
                     </MDEObjects>
                </MDEConfiguration>

will create an insertable object at ``OME:Image`` object

|mde_customObj|

that has input form for two specify key-value pairs

|mde_customObj2|

   
**Type of input fields**
-----------------------------

There are different editor input field types for the element ``<TagData>``. 

|mde_availableInputFields|

You can specify the different types like:

 `TextField` define like::
  
                <TagData DefaultValues=""
                        Name="Tag of Type TextField"
                        Type="TextField"
                        Unit=""
                        Value=""
                        Visible="true" />

 `TextField with unit` define like::

                <TagData DefaultValues=""
                        Name="Tag of Type TextField with unit"
                        Type="TextField"
                        Unit="nm"
                        Value=""
                        Visible="true" />

 `TextArea` define like::

      <TagData DefaultValues=""
                Name="Tag of Type TextArea"
                Type="TextArea"
                Unit=""
                Value=""
                Visible="true" />

 `ArrayField` define like (for an array of 2 elements)::

    <TagData DefaultValues="2"
              Name="Tag of Type ArrayField"
              Type="ArrayField"
              Unit=""
	      Value=""
              Visible="true" />

 `ArrayField` with unit define like (for an array of 3 elements)::

    <TagData DefaultValues="3"
              Name="Tag of Type ArrayField with unit"
              Type="ArrayField"
              Unit="s"
	      Value=""
              Visible="true" />

 `ComboBox` define like::

    <TagData DefaultValues="Value1,Value2,Value3"
    	      Name="tag of Type ComboBox"
              Type="ComboBox"
              Unit=""
              Value=""
              Visible="true" />

 `TimeStamp` define like::

    <TagData DefaultValues=""
              Name="Tag of Type TimeStamp"
              Type="TimeStamp"
              Unit=""
              Value=""
              Visible="true" />

.. |mde_availableInputFields| image:: images/mde_availableInputFields.PNG
.. |mde_customObj| image:: images/mde_customObj.png
.. |mde_customObj2| image:: images/mde_customObj2.png
