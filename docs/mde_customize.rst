Customize OMERO.mde
===================

Description
-----------

You can configurate and customize the OMERO.mde by defining and configurating elements in a ``mdeConfiguration.xml`` file. A template of this file can be found in the ``config/`` directory of the installed OMERO.insight installation or
at `mdeConfiguration.xml <https://github.com/ome/omero-insight/tree/master/src/config/mdeConfiguration.xml>`__.

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

The location of the configuration file should be in the ``config/`` folder or ``<userHome>/omero/``.
Please specify the location you will use by editing ``container.xml`` and ``containerImporter.xm``. To use ``config/`` as location::

    <!-- mde config file location (. for in config dir; omero for local user omero dir) -->
        <entry name="omero.client.import.mde.path">.</entry>

or for ``<userHome>/omero/`` as location::

    <!-- mde config file location (. for in config dir; omero for local user omero dir) -->
        <entry name="omero.client.import.mde.path">omero</entry>

and save the files.
Here we will use ``config/`` as location for ``mdeConfiguration.xml``.
Save the configuration file under ``config/`` and restart the OMERO.mde to load the custom configurations.

You can customize the OMERO.mde in following point:

.. toctree::
     :maxdepth: 1

     mde_customizeView
     mde_customizeObjects
     mde_predefineObjects
