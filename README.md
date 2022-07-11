# Вступление

Большая часть этого руководства касается принтеров, работающих на **Klipper**.

Это руководство изначально писалось для сообщества Voron, но все разделы настоек должны работать на **любом принтере под управлением Klipper**. Однако, некоторые заметки и советы касающиеся аппаратной части - все равно относятся именно к Voron принтерам. 
## Заметки

- Мой SuperSlicer профиль находится тут [:page_facing_up:here](https://github.com/AndrewEllis93/Ellis-PIF-Profile).

- Если у вас есть вопросы, комментарии или предложения касающиеся руководства, пожалуйста напишите мне или в GitHub issues или через Discord: [:page_facing_up:Ellis#4980](https://discordapp.com/users/207622442842062849)
    - Для вопросов **не касающихся непосредственно содержимого руководства как такового**, или по вопросам советов по устранению проблем и помощи в печати, пожалуйста используйте наш паблик канал в [:page_facing_up:Voron Discord](https://discord.gg/voron) (или подходящее сообщество по вашему принтеру). 
    - Я не могу быть персональными помощником каждому - на пабликах тусуется множество людей, которые могут помочь!

- Модели столов и текстуры, которые я использую, можно найти тут [:page_facing_up:Hartk's GitHub repo](https://github.com/hartk1213/MISC/tree/main/Voron%20Mods/SuperSlicer). Текстуры столов, которые я использовал ранее можно найти тут [:page_facing_up:VoronUsers.](https://github.com/VoronDesign/VoronUsers/tree/master/slicer_configurations/PrusaSlicer/hartk1213/V0/Bed_Shape) 

- Спасибо **bythorsthunder** что помогал отлаживать технологии и делал фотографии.

- Поддержка моей привычки прибухнуть:
[![](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/paypalme/AndrewEllis93)

## Иконки
- :warning: = **:exclamation:Пожалуйста, обратите особое внимание если видите этот знак.:exclamation:**

- :page_facing_up: = Линк на другую страницу.

- :pushpin: = Переход на другую секцию (на той же странице).

# Содержание
- [Перед началом](/articles/before_we_begin.md)
    - **:warning: Необходимые условия**
- [Примечание О Ширине Линии](/articles/a_note_about_line_width.md)
- [Установка Ожиданий](/articles/setting_expectations.md)
- [Voron V2 Выравнивание Портала](/articles/voron_v2_gantry_squaring.md)
- **Настройка печати** \
*Essentials. Read/follow these in order shown.*
    - [Build Surface Adhesion](/articles/build_surface_adhesion.md)
    - [First Layer Squish](/articles/first_layer_squish.md)
    - [Pressure Advance](/articles/pressure_advance.md)
        - Lines Method
        - Tower Method
        - Fine-Tuning and What to Look For
    - [Extrusion Multiplier](/articles/extrusion_multiplier.md)
        - Background 
        - Methods I'm Not a Fan Of
        - Method
    - [PA / EM Oddities](/articles/pa_em_oddities.md)
        - Slight Perimeter Gapping
        - Slight Corner Gapping
    - [Cooling and Layer Times](/articles/cooling_and_layer_times.md)
        - Signs of Overheating
        - How to Fix It
    - [Retraction](/articles/retraction.md)
    - [Infill/Perimeter Overlap](/articles/infill_perimeter_overlap.md)
- **Printer Tuning**\
*Mostly optional. For pushing limits, or for troubleshooting.\
"Voron V2 Gantry Squaring" is the only essential.*
    - [Determining Maximum Volumetric Flow Rate](/articles/determining_max_volumetric_flow_rate.md)
        - Why?
        - Approximate Values
        - How Volumetric Flow Rate Relates to Print Speed
        - Formulas
        - Method
        - Theory vs Reality
    - [Determining Motor Currents](/articles/determining_motor_currents.md)
        - Determining Initial `run_current`
        - Determining Maximum `run_current`
        - Determining `hold_current`
    - [Determining Maximum Speeds and Accelerations](/articles/determining_max_speeds_accels.md)
        - Method
        - Usage of the `TEST_SPEED` Macro
    - [Voron V2 Gantry Squaring](/articles/voron_v2_gantry_squaring.md)

- **Miscellaneous**
    - [Useful Macros](/articles/useful_macros.md)
        - Conditional Homing
        - Conditional QGL
        - Beeper
        - LCD RGB
        - My Pause/Resume Macros (For Runouts, Filament Swaps, and Manual Pauses)
            - M600 (Filament Change) Alias
            - Example Filament Sensor Config
                - Basic Filament Switch Sensor
                - Smart Filament Sensor
            - Pause
            - Resume
            - Cancel
            - Octoprint Configuration 
        - Filament Sensor Management
        - Parking
        - Off
        - Shut Down Pi
            - As option in LCD menu
        - Dump Parameters
        - Replace `M109`/`M190` With `TEMPERATURE_WAIT`
    - [Passing Slicer Variables to PRINT_START](/articles/passing_slicer_variables.md)
        - Passing Temperatures
            - SuperSlicer
            - Prusa Slicer
            - Cura
    - [Controlling Slicer Temperature G-Code Order (Simple Method)](/articles/controlling_slicer_g-code_order.md)
    - [My Setup](/articles/my_setup.md) (since people ask a lot)

- **Troubleshooting**\
*Even without issues, it's worth looking through some of these to familiarize yourself with things to look out for. **Especially** thermal drift under "First Layer / Squish Consistency Issues"*
    - [BMG Clockwork Backlash Issues (Repeating Patterns / "Wood Grain")](/articles/troubleshooting/bmg_clockwork_backlash.md)
    - [Bulging](/articles/troubleshooting/bulging.md)
        - Bulging Layers
        - Bulges at STL Vertices
        - Bulging Patterns on Overhangs (SS)
    - [Crimps](/articles/troubleshooting/crimps.md)
    - [Error: "Command Format Mismatch"](/articles/troubleshooting/command_format_mismatch.md)
    - [Extruder Skipping](/articles/troubleshooting/extruder_skipping.md)
    - [First Layer / Squish Consistency Issues](/articles/troubleshooting/first_layer_squish_consistency.md)
        - Thermal Drift
        - First Layer Conistency
        - Squish Consistency (Between Prints)
    - [Layer Shifting](/articles/troubleshooting/layer_shifting.md)
        - Mechanical
        - Speeds and Accelerations
        - Electrical
    - [PLA is Overheating](/articles/troubleshooting/pla_overheating.md)
    - [Pockmarks](/articles/troubleshooting/pockmarks.md)
    - [VFAs (Vertical Fine Artifacts)](/articles/troubleshooting/vfas.md)
        - Repeating VFAs With ~2mm Spacing
        - Repeating VFAs With Non-2mm Spacing
    - [Slicer is Putting Heating G-codes in the Wrong Place/Order](/articles/troubleshooting/slicer_putting_heating_g-codes_wrong_order.md)
    - [Small Infill Areas Look Overextruded](/articles/troubleshooting/small_infill_areas_overextruded.md)
