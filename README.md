# mcef-resources

Download mirror for **MCEF 1.7.10** (montoyo's CEF browser mod) CEF/JCEF binaries.
The original download host `montoyo.net` is very slow/unstable from mainland China; this repo mirrors the exact files so MCEF can be pointed at GitHub.

**All files are byte-for-byte copies of the originals. Copyright belongs to the MCEF/JCEF/CEF authors; this repository is a download mirror only.**

## What MCEF 1.7.10 actually downloads

Deployed jar `MCEF-1.7.10` (0.7, modid `MCEF`) builds URLs as `<mirror>/<resource>` where `<resource>` is:

- `config2.json` (remote config; the `"0.6"` key is used for MC 1.7.10)
- `0.6/<platform>/<file>` for every missing resource, platform = `win32` / `win64` / `linux64`

Original mirror root: `https://montoyo.net/jcef` (hardcoded `MONTOYO` entry in `net/montoyo/mcef/remote/Mirror`; config key `forcedMirror` overrides it).
Files land in the Minecraft game dir and are verified against the **SHA-1** values inside `config2.json`.

## This mirror

Release tag **v1** carries every file as a release asset, named `0.6-<platform>-<file>` (GitHub asset names cannot contain `/`; the leading `0.6` is the MCEF resource version directory).
A small ASM patch (`PatchMirror.java`, see MCEF-PATCH-NOTES.md in the mcphone-addon-browser project) makes MCEF translate `0.6/win64/cef.pak` -> `0.6-win64-cef.pak` when `forcedMirror` is set; `config2.json` is requested flat and unmodified.
Direct download example: `https://github.com/skyc10/mcef-resources/releases/download/v1/0.6-win64-libcef.dll`

### File manifest (SHA-1 = values in config2.json, used by MCEF itself; SHA-256 for independent verification)


| File (in release v1) | Original URL | Size (bytes) | SHA-1 (MCEF) | SHA-256 |
|---|---|---:|---|---|
| `0.6-win32-cef.pak` | `https://montoyo.net/jcef/0.6/win32/cef.pak` | 1894141 | `35e7111a7d6fdd81cb6fcfc87497600cdab7456b` | `ca5618a8f1d4681464fb3bf1927e8a1d7ebc2550ed56669a1d917d1591222861` |
| `0.6-win32-cef_100_percent.pak` | `https://montoyo.net/jcef/0.6/win32/cef_100_percent.pak` | 427877 | `2ee3e69b1ff8aa82ef4cae62975aac4d90290222` | `ba777c0eef8d990ac7a3bea788e590beb01a533792f5c9549fdd6f5be2f2f21e` |
| `0.6-win32-cef_200_percent.pak` | `https://montoyo.net/jcef/0.6/win32/cef_200_percent.pak` | 580316 | `69b1d9f37b52159904c843f031d1e50c3ab0ab1c` | `6dae82ae39535901aeb449f2854880a5f6c7a9e1640604161c83139280bbc3aa` |
| `0.6-win32-d3dcompiler_43.dll` | `https://montoyo.net/jcef/0.6/win32/d3dcompiler_43.dll` | 2106216 | `98be17e1d324790a5b206e1ea1cc4e64fbe21240` | `2f23182ec6f4889397ac4bf03d62536136c5bdba825c7d2c4ef08c827f3a8a1c` |
| `0.6-win32-d3dcompiler_46.dll` | `https://montoyo.net/jcef/0.6/win32/d3dcompiler_46.dll` | 3231832 | `9dcd5b3a05b4fd1c71198fc11aa0f8f569a3e21d` | `60f76ec7169397c425023d5927a3c3c34599fa329814053cace6171e20adb353` |
| `0.6-win32-devtools_resources.pak` | `https://montoyo.net/jcef/0.6/win32/devtools_resources.pak` | 5021737 | `842499621764622b33a2bcd55fc131925f98f310` | `9c18394c52da9154893c76f856009cac772d47c2db354d7463400e03ebbf5ee9` |
| `0.6-win32-ffmpegsumo.dll` | `https://montoyo.net/jcef/0.6/win32/ffmpegsumo.dll` | 985600 | `53b4650870481c5b98e0e5a9e10164298597eb5a` | `f31350774f1b7dcd0ce0e2bb64cc515376b40af55bd78a96e100f0c6b1024277` |
| `0.6-win32-icudtl.dat` | `https://montoyo.net/jcef/0.6/win32/icudtl.dat` | 10490576 | `1ecbe1bd741c7101c72361d1d3dab5ad9056c2a1` | `7bf5d5a1040bd328eec6b479967b4a585fb0ba13b3c42b6fca9231df2269303c` |
| `0.6-win32-jcef.dll` | `https://montoyo.net/jcef/0.6/win32/jcef.dll` | 456192 | `df7e928433c2adae617c7f0042c9c19a525262f5` | `8b503b442d615ee2e03db7dce2b1c3a0cf182b5a3c575337e28fd349f094ea39` |
| `0.6-win32-jcef_helper.exe` | `https://montoyo.net/jcef/0.6/win32/jcef_helper.exe` | 287232 | `eff10c426131809ff676b8826a87dd2f5e82b028` | `e7609fe3c145f3d32e2c2a65bd1f14992b861aaf72917f49212767a024bddae4` |
| `0.6-win32-libEGL.dll` | `https://montoyo.net/jcef/0.6/win32/libEGL.dll` | 212992 | `d0385658e88dca2df63b1aa39fe6506ccc93e791` | `a5f000705991e895ea75155fd81433195474eb69a675a0792411369df0aa3046` |
| `0.6-win32-libGLESv2.dll` | `https://montoyo.net/jcef/0.6/win32/libGLESv2.dll` | 1359872 | `45da37ad25345fadad8d9228fda9bed1d24fcb03` | `7c802c888fbec948ef6b5a934093f3db5db6f542746b6da29292b4367706fe89` |
| `0.6-win32-libcef.dll` | `https://montoyo.net/jcef/0.6/win32/libcef.dll` | 40558080 | `4edf7494c42c4eaa69e9bafa70badef117579b2d` | `e944ee5d7b37aafadf4111a3754379e00940998d0635fcf1db97ed8e6d81542e` |
| `0.6-win32-locales.zip` | `https://montoyo.net/jcef/0.6/win32/locales.zip` | 361538 | `fbe947b00b558949cda51462430bfdff1d30547e` | `35b761e6697c4b110a5b211957c6a1e1d6b39eb97ff201736c4b351ab12fabcc` |
| `0.6-win32-pdf.dll` | `https://montoyo.net/jcef/0.6/win32/pdf.dll` | 9301504 | `ff19418182dad96cd43e485f488010855196c6be` | `d507e2f7796237a155be37e0f4af2440057b3cc5447c060e2a24b51e5ff3560f` |
| `0.6-win64-cef.pak` | `https://montoyo.net/jcef/0.6/win64/cef.pak` | 1894141 | `35e7111a7d6fdd81cb6fcfc87497600cdab7456b` | `ca5618a8f1d4681464fb3bf1927e8a1d7ebc2550ed56669a1d917d1591222861` |
| `0.6-win64-cef_100_percent.pak` | `https://montoyo.net/jcef/0.6/win64/cef_100_percent.pak` | 427877 | `2ee3e69b1ff8aa82ef4cae62975aac4d90290222` | `ba777c0eef8d990ac7a3bea788e590beb01a533792f5c9549fdd6f5be2f2f21e` |
| `0.6-win64-cef_200_percent.pak` | `https://montoyo.net/jcef/0.6/win64/cef_200_percent.pak` | 580316 | `69b1d9f37b52159904c843f031d1e50c3ab0ab1c` | `6dae82ae39535901aeb449f2854880a5f6c7a9e1640604161c83139280bbc3aa` |
| `0.6-win64-d3dcompiler_43.dll` | `https://montoyo.net/jcef/0.6/win64/d3dcompiler_43.dll` | 2106216 | `98be17e1d324790a5b206e1ea1cc4e64fbe21240` | `2f23182ec6f4889397ac4bf03d62536136c5bdba825c7d2c4ef08c827f3a8a1c` |
| `0.6-win64-d3dcompiler_46.dll` | `https://montoyo.net/jcef/0.6/win64/d3dcompiler_46.dll` | 3873368 | `9ced490f112005df9576d16ee06d8004db44afbe` | `7a9bae7907abd79d15d9d4114674d3fc01f0438d76bc5afdf827bbfa7fc3b020` |
| `0.6-win64-devtools_resources.pak` | `https://montoyo.net/jcef/0.6/win64/devtools_resources.pak` | 5021737 | `842499621764622b33a2bcd55fc131925f98f310` | `9c18394c52da9154893c76f856009cac772d47c2db354d7463400e03ebbf5ee9` |
| `0.6-win64-ffmpegsumo.dll` | `https://montoyo.net/jcef/0.6/win64/ffmpegsumo.dll` | 1015296 | `19a5e8a58c2a26a1a4039614caf10b06421a3b00` | `3ce159c9fddc8fc4f4fcea371801cd1d33a1181fee94ad269465d9430d094858` |
| `0.6-win64-icudtl.dat` | `https://montoyo.net/jcef/0.6/win64/icudtl.dat` | 10490576 | `1ecbe1bd741c7101c72361d1d3dab5ad9056c2a1` | `7bf5d5a1040bd328eec6b479967b4a585fb0ba13b3c42b6fca9231df2269303c` |
| `0.6-win64-jcef.dll` | `https://montoyo.net/jcef/0.6/win64/jcef.dll` | 613376 | `eb2196dbaee4fc88bbe78ca1d2b2671d57795111` | `ea97975d8f1f060c566fba75583e850efb18f8dcc82b4e79ccd77be78e39d351` |
| `0.6-win64-jcef_helper.exe` | `https://montoyo.net/jcef/0.6/win64/jcef_helper.exe` | 374784 | `d96ad53efa97d8357c5f2ddda47a4d396f8f8076` | `3ba97124ff4ce60d1a2148d9872261ddca639468838a447b1e0e35f26310ed1c` |
| `0.6-win64-libEGL.dll` | `https://montoyo.net/jcef/0.6/win64/libEGL.dll` | 208896 | `505cf7e18d0fea964b0cc80aeef4a69701dc2a80` | `fb87cba9dbbdf6c6cc78444a866f3a4018361fe303b737f70f6268ebca38657f` |
| `0.6-win64-libGLESv2.dll` | `https://montoyo.net/jcef/0.6/win64/libGLESv2.dll` | 1750016 | `ff159e7940bbfed3e9d80771dafba0449ffdd7f7` | `256895cd9d7d20d0a92aea2f79c4a926ca4a38d3e193999980a8d720608d5047` |
| `0.6-win64-libcef.dll` | `https://montoyo.net/jcef/0.6/win64/libcef.dll` | 53328384 | `d1ea4e67de9572e65cea04eaec809ff1dce9d9e0` | `7b483e717f07063d606e538d8c0a8fe99f7771105f5dc77a34d3e20908b85445` |
| `0.6-win64-locales.zip` | `https://montoyo.net/jcef/0.6/win64/locales.zip` | 361538 | `d541cbec7113ec14d3a7f79b10be67e27ac37cee` | `a6bdf9a88efd3aca626c894636ee71af23d107eb0537c226f80d51a6f301566f` |
| `0.6-win64-pdf.dll` | `https://montoyo.net/jcef/0.6/win64/pdf.dll` | 11211776 | `69ca1429ade0be98ec253c5f58b76a8943b0dad4` | `fa059e7f16e18fa8d5fd96b6571e747e9643416ab55e07706a49ed9240ef55e6` |
| `0.6-linux64-cef.pak` | `https://montoyo.net/jcef/0.6/linux64/cef.pak` | 2161084 | `7804c134a0ac52caf3cec28a7eae75547a03125d` | `3755d0e49d0b973ce89982cf7499c0a44c9b7f94546c1f560d921e6f7111d7ac` |
| `0.6-linux64-cef_100_percent.pak` | `https://montoyo.net/jcef/0.6/linux64/cef_100_percent.pak` | 314151 | `a442628aefa628aef1ee35a071b7f9c45db617cd` | `aa2d81579eefbdbb70bf0ac979b55b8dd141268590a0f6d2447f7c9e485871d6` |
| `0.6-linux64-cef_200_percent.pak` | `https://montoyo.net/jcef/0.6/linux64/cef_200_percent.pak` | 409257 | `0a7a66cf596567d57833e57eaeae2f5904ec9201` | `35c4768e7c8c3580c58eed877b0f34150f9cb20a93206fdcb66f7bca6d73a724` |
| `0.6-linux64-chrome-sandbox` | `https://montoyo.net/jcef/0.6/linux64/chrome-sandbox` | 20000 | `90c083edf9ac6e9037db59691f5844f217794621` | `d85f6c85f4e5a55886a48c784a11d10acb798d3a6d6a6dfd3b1e466794e7a03c` |
| `0.6-linux64-devtools_resources.pak` | `https://montoyo.net/jcef/0.6/linux64/devtools_resources.pak` | 4377423 | `4f49df1670e648dfd7c1236c1e0a559fa06fa081` | `10a21da245db2fb7c136252d9c5d07d5160e70e23244444d5f94de0a5225db9f` |
| `0.6-linux64-icudtl.dat` | `https://montoyo.net/jcef/0.6/linux64/icudtl.dat` | 10206624 | `22c8b378d1695e0f94ae8d52c9480eccff92f62c` | `18977bd65e2b2ceb2821db501dfd2bdd920762972e612dd1d8ec45f4a313296f` |
| `0.6-linux64-jcef_helper` | `https://montoyo.net/jcef/0.6/linux64/jcef_helper` | 516256 | `5a95eb493125c3f7bf797e673129a2b513d8f528` | `2b10bf68d56fcbf0c828559bc8d0b0de16598c536c5f4fadaf64ff6c546e001e` |
| `0.6-linux64-libcef.so` | `https://montoyo.net/jcef/0.6/linux64/libcef.so` | 106368800 | `94c6d5cccf3158f5db8bcf2d746b7083f699e84a` | `ecdbcad78edea4c3bcb5aa50fe6089dcefabb535b8f07658646b2ee1a8c2fca5` |
| `0.6-linux64-libjcef.so` | `https://montoyo.net/jcef/0.6/linux64/libjcef.so` | 1113680 | `960521a1d8ced95612da2573a338ae97596f8835` | `394753d3590040b4ef26e2980b6c8629319814fb82e66b5bec466a65c9d77533` |
| `0.6-linux64-locales.zip` | `https://montoyo.net/jcef/0.6/linux64/locales.zip` | 524672 | `3c879f079c19ef743174ef7f48f0acde7573698c` | `ad06ea95e66ee6c233cc789f10260194a2e3c469d0b327ca70879868c5c4916a` |
| `0.6-linux64-natives_blob.bin` | `https://montoyo.net/jcef/0.6/linux64/natives_blob.bin` | 410849 | `d04538ee75d54587472ef1bbfe343b087e40d5fd` | `309a304a5e4ed8688ecb60064c4118598a606b7914b37b9cbe577898f9f30e01` |
| `0.6-linux64-snapshot_blob.bin` | `https://montoyo.net/jcef/0.6/linux64/snapshot_blob.bin` | 587068 | `b2ce2dfebad637ca9402f9f206beb49c3af902e2` | `357ad8771a199a075b5f091a4daab4b9476ee19b60edd25ad992bafe76add074` |
| `config2.json` | `https://montoyo.net/jcef/config2.json` | 12896 | n/a (is the checksum source) | `c408ce8fa5f64788ec1918eaa3614d766bcb527415db505af37f8013f3294608` |
| `SHA256SUMS.txt` | generated | - | - | standard `sha256sum` format |

Total payload: 297543866 bytes (283.8 MiB), 42 files. All 42 verified against config2.json SHA-1 after download, and re-verified against GitHub's reported SHA-256 asset digests after upload.

## config2.json note

The mirrored `config2.json` is identical to the original, so MCEF's SHA-1 verification keeps working unchanged. If montoyo.net publishes new versions later, this mirror will not auto-update.
