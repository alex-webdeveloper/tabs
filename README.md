# tabs

tabs(".info-header", ".info-header-tab", ".info-tabcontent", "flex");

function tabs(ClassTabsParent, ClassTabs, ClassTabsContent, disp = "block") {
    let tabsParent = document.querySelector(ClassTabsParent);
    let tabs = document.querySelectorAll(ClassTabs);
    let tabsContent = document.querySelectorAll(ClassTabsContent);

    function hideTabsContent(index) {
        for (let i = index; i < tabsContent.length; i++) {
            // tabsContent[i].classList.remove("show");
            // tabsContent[i].classList.add("hide");
            tabsContent[i].style.display = "none";
        }
    };
    hideTabsContent(1);

    function showTabsContent(index) {
        // if (tabsContent[index].classList.contains("hide")) {
        //     tabsContent[index].classList.remove("hide");
        //     tabsContent[index].classList.add("show");
        // }
        if (tabsContent[index].style.display == "none") {
            tabsContent[index].style.display = disp;
        }
    };

    tabsParent.addEventListener("click", function (e) {
        let target = e.target;
        if (target && target.classList.contains("info-header-tab")) {
            for (let i = 0; i < tabs.length; i++) {
                if (target == tabs[i]) {
                    hideTabsContent(0);
                    showTabsContent(i);
                    break;
                }
            }
        }
    })
}
