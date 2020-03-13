Customize OMERO.mde
======================

**Description**
---------------------

You can configurate and customize the OMERO.mde by define and configurate elements in a mdeConfiguration.xml file. A template of this file can be found at https://github.com/sukunis/omero-insight/blob/feat_MDE/mdeConfiguration.xml.

Structure of mdeConfiguration.xml::

            <?xml version="1.0" encoding="UTF-8"?>
                <MDEConfiguration>
                    <MDEPredefinitions> <!-- Predefinitions for properties of objects group by setups--!>
                        <SetupPre Name="SetupName">
                            <ObjectPre>
                                <TagData.../>
                                ...
                            </ObjectPre>
                            ...
                        </SetupPre>
                        ...
                    </MDEPredefinitions>
                    <MDEObjects>
                        <Definitions> <!-- Definitions of objects, properties and hierarchy--!>
                            <ObjectDef Type="ObjectName">
                                <TagData.../>
                                ...
                                <Parents.../>
                            </ObjectDef>
                            ...
                        </Definitions>
                        <Configurations> <!--Definition of setups and configuration of objects and properties belonging to the setup --!>
                            <SetupConf Name="SetupName">
                                <ObjectConf Type="ObjectName">
                                    <TagDataProp.../>
                                    ...
                                </ObjectConf>
                                ...
                            </SetupConf>
                            ...
                        </Configurations>
                    </MDEObjects>
                </MDEConfiguration>

Save the configuration file under *<userHome>/omero/* and restart the OMERO.mde to load custom configurations.

You can customize the OMERO.mde in following point:

.. toctree::
     :maxdepth: 1

     mde_customizeView
     mde_customizeObjects
     mde_predefineObjects
