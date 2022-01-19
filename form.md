<?xml version="1.0" encoding="UTF-8"?>
<!--
/*
 * SussexDev_Sample
 * @category   SussexDev
 * @package    SussexDev_Sample
 * @copyright  Copyright (c) 2019 Scott Parsons
 * @license    https://github.com/ScottParsons/module-sampleuicomponent/blob/master/LICENSE.md
 * @version    1.1.2
 */
-->
<form xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
    <argument name="data" xsi:type="array">
        <item name="js_config" xsi:type="array">
            <item name="provider" xsi:type="string">maksarov_form.maksarov_form_data_source</item>
            <item name="deps" xsi:type="string">maksarov_form.maksarov_form_data_source</item>
        </item>
        <item name="label" xsi:type="string" translate="true">Sample Form</item>
        <item name="layout" xsi:type="array">
            <item name="type" xsi:type="string">tabs</item>
        </item>
    </argument>
    <settings>
        <buttons>
            <button name="save_and_continue" class="Magento\Customer\Block\Adminhtml\Edit\SaveAndContinueButton"/>
            <button name="save" class="Maksarov\UiComponentExample\Block\Adminhtml\Buttons\SaveButton"/>
            <button name="reset" class="Magento\Customer\Block\Adminhtml\Edit\ResetButton"/>
            <button name="order" class="Magento\Customer\Block\Adminhtml\Edit\OrderButton"/>
            <button name="resetPassword" class="Magento\Customer\Block\Adminhtml\Edit\ResetPasswordButton"/>
            <button name="unlock" class="Magento\Customer\Block\Adminhtml\Edit\UnlockButton"/>
            <button name="invalidateToken" class="Magento\Customer\Block\Adminhtml\Edit\InvalidateTokenButton"/>
            <button name="delete" class="Magento\Customer\Block\Adminhtml\Edit\DeleteButton"/>
            <button name="back" class="Magento\Customer\Block\Adminhtml\Edit\BackButton"/>
        </buttons>
    </settings>
    <dataSource name="maksarov_form_data_source">
        <argument name="dataProvider" xsi:type="configurableObject">
            <argument name="class" xsi:type="string">Maksarov\UiComponentExample\Model\DataProvider</argument>
            <argument name="name" xsi:type="string">maksarov_form_data_source</argument>
            <argument name="primaryFieldName" xsi:type="string">id</argument>
            <argument name="requestFieldName" xsi:type="string">id</argument>
        </argument>
        <argument name="data" xsi:type="array">
            <item name="js_config" xsi:type="array">
                <item name="component" xsi:type="string">Magento_Ui/js/form/provider</item>
            </item>
        </argument>
    </dataSource>
    <fieldset name="sample_fieldset">



        <argument name="data" xsi:type="array">
            <item name="config" xsi:type="array">
                <item name="label" xsi:type="string" translate="true">Sample Fieldset</item>
            </item>
        </argument>



        <!-- This field represents form id and is hidden -->
        <field name="entity_id">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="visible" xsi:type="boolean">false</item>
                    <item name="dataType" xsi:type="string">text</item>
                    <item name="formElement" xsi:type="string">input</item>
                    <item name="source" xsi:type="string">sampleform</item>
                </item>
            </argument>
        </field>

        <!-- This field has data type 'text' and standard 'input' form element and looks like input -->
        <field name="title">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="label" xsi:type="string">Some text</item>
                    <item name="visible" xsi:type="boolean">true</item>
                    <item name="dataType" xsi:type="string">text</item>
                    <item name="formElement" xsi:type="string">input</item>
                    <item name="source" xsi:type="string">sampleform</item>
                </item>
            </argument>
        </field>



        <field name="myCheckbox" formElement="checkbox">
            <settings>
                <label translate="true">Enabled</label>
                <tooltip>
                    <description translate="true">This is my checkbox's description</description>
                </tooltip>
            </settings>
            <formElements>
                <checkbox>
                    <settings>
                        <prefer>toggle</prefer>
                        <valueMap>
                            <map name="false" xsi:type="boolean">false</map>
                            <map name="true" xsi:type="boolean">true</map>
                        </valueMap>
                    </settings>
                </checkbox>
            </formElements>
        </field>


        <checkboxset name="checkboxset_example">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="additionalInfo" xsi:type="string">Additional information</item>
                </item>
            </argument>
            <settings>
                <label translate="true">Checkboxset Component Example</label>
                <options>
                    <option name="0" xsi:type="array">
                        <item name="value" xsi:type="number">1</item>
                        <item name="label" xsi:type="string" translate="true">Option #1</item>
                    </option>
                    <option name="1" xsi:type="array">
                        <item name="value" xsi:type="number">2</item>
                        <item name="label" xsi:type="string" translate="true">Option #2</item>
                    </option>
                    <option name="2" xsi:type="array">
                        <item name="value" xsi:type="number">3</item>
                        <item name="label" xsi:type="string" translate="true">Option #3</item>
                    </option>
                </options>
            </settings>
        </checkboxset>

        <email name="email_example">
            <settings>
                <label translate="true">Email Field Example</label>
            </settings>
        </email>




        <fileUploader name="file_example">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="label" xsi:type="string">File Field</item>
                    <item name="visible" xsi:type="boolean">true</item>
                    <item name="formElement" xsi:type="string">fileUploader</item>
                    <item name="uploaderConfig" xsi:type="array">
                        <item name="url" xsi:type="url" path="path/to/controller"/>
                    </item>
                </item>
            </argument>
        </fileUploader>




        <field name="multiselect_example" formElement="multiselect">
            <settings>
                <dataType>text</dataType>
                <label translate="true">Multiselect Example</label>
                <dataScope>multiselect_example</dataScope>
            </settings>
            <formElements>
                <multiselect>
                    <settings>
                        <options>
                            <option name="1" xsi:type="array">
                                <item name="value" xsi:type="string">1</item>
                                <item name="label" xsi:type="string">Option #1</item>
                            </option>
                            <option name="2" xsi:type="array">
                                <item name="value" xsi:type="string">2</item>
                                <item name="label" xsi:type="string">Option #2</item>
                            </option>
                            <option name="3" xsi:type="array">
                                <item name="value" xsi:type="string">3</item>
                                <item name="label" xsi:type="string">Option #3</item>
                            </option>
                        </options>
                    </settings>
                </multiselect>
            </formElements>
        </field>



        <field name="text_example" formElement="input" sortOrder="10">
            <settings>
                <elementTmpl>ui/form/element/text</elementTmpl>
                <label translate="true">Text Field Example</label>
            </settings>
        </field>


        <field name="textarea_example">
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="formElement" xsi:type="string">textarea</item>
                    <item name="cols" xsi:type="number">15</item>
                    <item name="rows" xsi:type="number">5</item>
                    <item name="label" translate="true" xsi:type="string">Textarea Field Example</item>
                    <item name="dataType" translate="true" xsi:type="string">text</item>
                </item>
            </argument>
        </field>
    </fieldset>



    <!-- dynamicRows -->

    <!-- dynamicRows -->


</form>
