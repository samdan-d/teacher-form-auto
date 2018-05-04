# teacher-form-auto
MUIS - Hicheel tandalt uguhud bugluh formiig automataar bugluh.

Parameters:
o_container - asuultuud aguulj bui element .
ans1 - ehnii textarea d oroh hariul, bagshiin tuhai.
ans2 - daraagiin  textarea d oroh hariul, surgaltiin orchin.
ans3 - daraagiin  textarea d oroh hariul, hicheeliin talaar.

Hiih uildel:
ans iig hargalzah textaread uguh.
Buh asuult deer hamgiin deed taliin hariultiig songono.

	function checkFirstElement(o_container, ans1, ans2, ans3) {
		var k = 0;
		var ans = [ans1, ans2, ans3];

		var container = document.querySelectorAll(o_container + '>UL');

		for (var i = 0; i < container.length; i++) {

			var asuultUL = container[i].querySelectorAll('LI>UL');

			for (var j = 0; j < asuultUL.length; j++) {
				var asuultLI = asuultUL[j].querySelectorAll('LI')[0];
				var firstInput = asuultLI.querySelector('input') || asuultLI.querySelector('textarea');
				if (firstInput.type === "radio") {
					firstInput.checked = true;
				}
				else {
					firstInput.value = ans[k];
					k++;
				}
			}
		}
	}

	// herhen heregleh ve?
	checkFirstElement('#questions', 'Sain bagsh', 'Haluun, bugchim, agaariin soliltsoo muutai', 'Sain');
