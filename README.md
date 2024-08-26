# G4GRASS
Github for GRASS (drought in Luxembourg and the Greater Region)

## Presentation of the hydrologic model

### SUPERFLEX model version history

<table border=0 cellpadding=0 cellspacing=0 width=1193 style='border-collapse:
 collapse;table-layout:fixed;width:895pt;mso-yfti-tbllook:1056'>
 <col width=235 style='mso-width-source:userset;mso-width-alt:8594;width:176pt'>
 <col width=200 style='mso-width-source:userset;mso-width-alt:4681;width:96pt'>
 <col width=257 style='mso-width-source:userset;mso-width-alt:9398;width:193pt'>
 <col width=157 style='mso-width-source:userset;mso-width-alt:5741;width:118pt'>
 <col width=416 style='mso-width-source:userset;mso-width-alt:15213;width:312pt'>
 <tr height=20 style='height:15.0pt'>
  <td height=20 width=235 style='height:15.0pt;width:176pt'></td>
  <td width=200 style='width:96pt'>Model extent</td>
  <td width=257 style='width:193pt'>Resolution / Timestep</td>
  <td width=157 style='width:118pt'>Number of parameters</td>
  <td width=416 style='width:312pt'>Notes</td>
 </tr>
 <tr height=20 style='height:15.0pt'>
  <td height=20 style='height:15.0pt'>CRAKE+GRASS</td>
  <td>Greater Region</td>
  <td>1km / Hourly</td>
  <td>8</td>
  <td rowspan=3 class=xl66 width=416 style='width:312pt'><span
  style='mso-special-format:bullet'>- <font class="font5">ERA5 P and PET</font><font
  class="font0"><br>
    - 5 land-use classes, 2 geology classes<br>
    - 4 reservoirs (2 UR, 1 FR, 1 SR)<br>
    - S1max = 5cm, S2max = 95 cm (fixed)<br>
    - Calibration over discharge (4 stations) and S1 SM data
 </font></span>
 </td>
 </tr>
 <tr height=20 style='height:15.0pt'>
  <td height=20 style='height:15.0pt'>GRASS</td>
  <td>Greater Region</td>
  <td rowspan=3 class=xl65>1km / Daily (timelag functions not used)</td>
  <td>9 (added Field capacity)</td>
 </tr>
 <tr height=20 style='height:15.0pt'>
  <td height=20 style='height:15.0pt'>GRASS (currently used for testing DA)</td>
  <td>Alzette sub-catchment</td>
  <td>9</td>
 </tr>
 <tr height=20 style='height:15.0pt'>
  <td height=20 style='height:15.0pt'>GRASS updated (TBD)</td>
  <td>Greater Region</td>
  <td>9</td>
  <td>Updating equations… + recalibration</td>
 </tr>
 <![if supportMisalignedColumns]>
 <![endif]>
</table>

### DA development version history

<table border=0 cellpadding=0 cellspacing=0 width=1159 style='border-collapse:
 collapse;table-layout:fixed;width:869pt;mso-yfti-tbllook:1056'>
 <col width=235 style='mso-width-source:userset;mso-width-alt:8594;width:176pt'>
 <col width=128 style='mso-width-source:userset;mso-width-alt:4681;width:96pt'>
 <col width=200 style='mso-width-source:userset;mso-width-alt:9398;width:193pt'>
 <col width=300 style='mso-width-source:userset;mso-width-alt:10971;width:225pt'>
 <col width=239 style='mso-width-source:userset;mso-width-alt:8740;width:179pt'>
 <tr height=20 style='height:15.0pt'>
  <td height=20 style='height:15.0pt'></td>
  <td class=xl68>Assimilation time</td>
  <td class=xl68>Observations</td>
  <td class=xl68>Control vector</td>
  <td class=xl68>Perturbation</td>
 </tr>
 <tr height=40 style='height:30.0pt'>
  <td height=40 style='height:30.0pt'>DA (first iteration)</td>
  <td>Monthly</td>
  <td>Q (in-situ)</td>
  <td>5 state vars</td>
  <td class=xl66 width=239 style='width:179pt'><span style='mso-special-format:
  bullet'>- <font class="font6">Gaussian, additive for P and PET. </font><font
  class="font0"><br>
    - 10 members</font></span></td>
 </tr>
 <tr height=40 style='height:30.0pt'>
  <td height=40 style='height:30.0pt'>DA (Nth iteration)</td>
  <td>Daily</td>
  <td class=xl66 width=257 style='width:193pt'>Q (in-situ)<br>
    SM (in-situ)</td>
  <td>5 state vars at all cells from the sub-catchment</td>
  <td rowspan=3 class=xl67 width=239 style='width:179pt'><span
  style='mso-special-format:bullet'>-<font class="font6"> Log-normal,
  multiplicative for P</font><font class="font0"><br>
    - Gaussian, additive for PET<br>
    - 10-50 members</font></span></td>
 </tr>
 <tr height=40 style='height:30.0pt'>
  <td height=40 style='height:30.0pt'>DA (Nth iteration)</td>
  <td>Daily</td>
  <td class=xl66 width=257 style='width:193pt'>Q (in-situ)<br>
    SM (in-situ)</td>
  <td>5 state vars + 1 param (&#961;)</td>
 </tr>
 <tr height=40 style='height:30.0pt'>
  <td height=40 style='height:30.0pt'>DA (last iteration)</td>
  <td>Daily</td>
  <td class=xl66 width=257 style='width:193pt'>SM (satellite)<br>
    GRACE</td>
  <td>5 state vars at all cells from the sub-catchment</td>
 </tr>
 <![if supportMisalignedColumns]>
 <![endif]>
</table>


