# objects-practice-tasks

# Link for advance level tasks  : 
https://github.com/Ameer255/objects-practice-tasks-advance

# Level basic and intermediate




// #LEVEL-1 Access methods
// Q1.

let arr = [5, 10, 15];

// Accessing third element
console.log(arr[2]);

// Q2.

let obj = {
    name: "Maimoona",
    degree: "MBBS"
}

// Accessing Degree property

console.log(obj.degree);

// Q3.

let arr2 = [1, 2, 3, 4, 5, 6, 7];

// Accessing each element of array using for loop

for (let i = 0; i < arr2.length; i++) {
    console.log(arr2[i]);
}

// Q4. 
let obj2 = {
    name: "Maimoona",
    degree: "MBBS",
    age: 25
};

                 
  for (const prop in obj2) {
  console.log(prop + " : "+ obj2[prop]);
                        }
                        

// LEVEL # INTERMEDIATE 

// Students names and hobbies data

let students1 = [
    {
        name: "Amna",
        hobbies: ["eating", "cooking"]
    },
    {
        name: "Daniyal",
        hobbies: ["arts", "shopping"]
    },
    {
        name: "Fahad",
        hobbies: ["coding", "cooking"]
    },
    {
        name: "Hajra",
        hobbies: ["sleep", "reading"]
    }
];

// Printing each student's data

students1.forEach((student) => {

    console.log("Hobbies of " + student.name);

    //using nested forEach for hobbies array

    student.hobbies.forEach((hobby, index) => {
        console.log((index + 1) + ". " + hobby);
    });

});




// Extensive students data

let students = [
    {
        name: "Amna",
        gender: "f",
        dob: new Date("02-04-1990"),
        address: {
            ilaqa: "Gulistan-e-Johar",
            city: "Karachi",
            country: "Pakistan",
            postalCode: 47114
        },
        phoneNo: "0331-2324243",
        admissionTestScore: 56,
        hasInternet: true,
        hasComputer: false,
        hasJob: true,
        hasSchoolBefore: false
    },
    {
        name: "Hadia",
        gender: "f",
        dob: new Date("05-15-1984"),
        address: {
            ilaqa: "Lyari",
            city: "Karachi",
            country: "Pakistan",
            postalCode: 75660
        },
        phoneNo: "0345-3452953",
        admissionTestScore: 48,
        hasInternet: false,
        hasComputer: false,
        hasJob: false,
        hasSchoolBefore: true
    },
    {
        name: "Ahmed",
        gender: "m",
        dob: new Date("06-27-2002"),
        address: {
            ilaqa: "University Road",
            city: "Quetta",
            country: "Pakistan",
            postalCode: 82215
        },
        phoneNo: "0333-0124325",
        admissionTestScore: 33,
        hasInternet: true,
        hasComputer: false,
        hasJob: false,
        hasSchoolBefore: false
    },
    {
        name: "Fariha",
        gender: "f",
        dob: new Date("09-13-1998"),
        address: {
            ilaqa: "University Road",
            city: "Karachi",
            country: "Pakistan",
            postalCode: 82215
        },
        phoneNo: "0331-9432532",
        admissionTestScore: 33,
        hasInternet: true,
        hasComputer: false,
        hasJob: false,
        hasSchoolBefore: false
    },
    {
        name: "Abdullah",
        gender: "m",
        dob: new Date("01-24-1972"),
        address: {
            ilaqa: "Bazar Colony",
            city: "Lahore",
            country: "Pakistan",
            postalCode: 32212
        },
        phoneNo: "0345-9912121",
        admissionTestScore: 33,
        hasInternet: false,
        hasComputer: false,
        hasJob: true,
        hasSchoolBefore: true
    }
];


// printing each student's data

students.forEach((student) => {

    console.log("Name : " + student.name);

    if (student.gender === "f") {
        console.log("Gender : Female");
    }

    else {
        console.log("Gender : Male");

    }

    console.log("City : " + student.address.city);

    console.log("Score : " + student.admissionTestScore + " marks");

    if (student.admissionTestScore >= 50) {
        console.log("Passed\n");
    }
    else {
        console.log("Failed\n");
    }
});



let femaleStudents = new Array();
let maleStudents = new Array();
let passStudents = new Array();
let eligibleStudents = new Array();
let studentsAddress = new Array();
let ufoneStudents = new Array();
let groupA = new Array();
let groupB = new Array();
let ageOfStudents = new Array();
let olderStudents = new Array();




students.forEach((student) => {

    // printing the names of female students only
    if (student.gender === "f") {
        femaleStudents.push(student.name);


    }
    else {

        // printing the names of male students only

        maleStudents.push(student.name);
    }


    // printing the names of students who have passed test
    if (student.admissionTestScore >= 50) {

        passStudents.push(student.name)
    }


    // printing the names of eligible students 
    if (student.address.city === "Karachi" && student.hasInternet) {

        eligibleStudents.push(student.name);

    }

    // printing student's Address



    studentsAddress.push(student.name + "'s address :\n" + student.address.ilaqa + " in " + student.address.city + ", " + student.address.country + "\n");


    let num = parseInt(student.phoneNo)

    // printing names of students who have ufone
    if (num >= 330 && num < 340) {

        ufoneStudents.push(student.name + "\n" + student.phoneNo);

    }

    // Printing the names of students in Group A, and in Group B
    if (student.hasJob || student.hasSchoolBefore) {
        groupB.push(student.name)
    }
    else {
        groupA.push(student.name);
    }

    let currentYear = new Date().getYear();
    // Printing age of each student 

    ageOfStudents.push(student.name + "'s age is " + (currentYear - student.dob.getYear()));


    // printing age of oldest student
    let age = 0;
    let oldest = " ";
    let currentAge = (currentYear - student.dob.getYear());

    if (currentAge > age) {

        age = currentAge;
        oldest = student.name + " is oldest, age : " + currentAge;
        olderStudents[0] = oldest;

    }


});


let derivedData = [
    {
        title: "Female students",
        data: femaleStudents
    },

    {
        title: "Male students",
        data: maleStudents
    },
    {
        title: "Passed students",
        data: passStudents
    },
    {
        title: "Eligible students",
        data: eligibleStudents
    },
    {
        title: "Students Address",
        data: studentsAddress
    },
    {
        title: "Ufone students",
        data: ufoneStudents
    },
    {
        title: "Group A",
        data: groupA
    },
    {
        title: "Group B",
        data: groupB
    },
    {
        title: "Students Ages",
        data: ageOfStudents
    },
    {
        title: "Oldest student",
        data: olderStudents
    },

];

derivedData.forEach((data) => {
    console.log(data.title);

    data.data.forEach((info) => {
        console.log(info);
    });
});



// VIDEOS DATA TASK


let videos = [
    {
        title: "Photoshop tutorial",
        lengthInMinutes: 70,
        category: "Education",
        uploadDate: new Date("08-14-2020"),
        tags: "design, digital, photoshop, creativity",
        features: ["Live", "360°", "HDR"],
        viewCount: 4700,
        rating: 4.8
    },


    {
        title: "Episode # 01 - The Best Comedy Show",
        lengthInMinutes: 2,
        category: "Entertainment",
        uploadDate: new Date("07-03-2019"),
        tags: "comedy, funny",
        features: ["Subtitles/CC", "3D", "HD"],
        viewCount: 145615,
        rating: 4.1
    },
    {
        title: "How to use FOR EACH loop - tutorial by Tech Karo",
        lengthInMinutes: 25,
        category: "Education",
        uploadDate: new Date("11-10-2018"),
        tags: "javascript, loops, web development",
        features: ["Purchased", "HD"],
        viewCount: 9004,
        rating: 4.3
    }
];


// Printing each video data
videos.forEach((video) => {

    console.log(`Title : ${video.title} `);
    console.log(`Length : ${video.lengthInMinutes} `);
    console.log(`Category : ${video.category} `);
    console.log(`Views : ${video.viewCount} `);
    console.log(`Uploaded On : ${video.uploadDate.getDate()}-${new Intl.DateTimeFormat('en-US', {month: "short"}).format(video.uploadDate)}-${video.uploadDate.getFullYear()} `);

    console.log(`Rating : ${video.rating} `);

});



// Printing short videos only
console.log("\nShort videos");

videos.forEach((video) => {
    if (video.lengthInMinutes < 3) {


        console.log(video.title);
    }
});


// Printing long videos only
console.log("\n Long videos");
videos.forEach((video) => {
    if (video.lengthInMinutes > 20) {


        console.log(video.title);
    }
});





// Printing longest videos only
let longestLength = 0;
let videoTitle = " ";

console.log("\nLongest video");
videos.forEach((video) => {
    if (video.lengthInMinutes > longestLength) {

        longestLength = video.lengthInMinutes;
        videoTitle = video.title;
    }
});


// Printing educational videos only
console.log(videoTitle);

console.log("\nEducational videos");
videos.forEach((video) => {

    if (video.category === "Education") {
        console.log(video.title);
    }

});


// Printing videos which contain tag "javascript"
console.log("\nVideos with JavaScript tag");

videos.forEach((video) => {

    if (video.tags.includes("javascript")) {
        console.log(video.title);
    }

});


// Printing videos which contain feature "HD"
console.log("\n Videos with HD feature");

videos.forEach((video) => {


    for (let j = 0; j < video.features.length; j++) {
        if (video.features[j] === "HD") {
            console.log(video.title);
        }
    }

});


// Printing videos which are uploaded today

console.log("\n today Uploaded videos ");
let todayDate = new Date("08-14-2020");

videos.forEach((video) => {
    let videoDate = video.uploadDate;

    if (videoDate.getMonth() == todayDate.getMonth() && videoDate.getDay() === todayDate.getDay() && videoDate.getYear() === todayDate.getYear()) {
        console.log(video.title);

    }

});



// Printing videos which are uploaded this month
console.log("\n Videos uploaded this month ");

videos.forEach((video) => {
    let videoDate = video.uploadDate;

    if (videoDate.getMonth() == todayDate.getMonth() && videoDate.getYear() === todayDate.getYear()) {
        console.log(video.title);

    }

});



// Printing videos which are uploaded this year
console.log("\nVideos uploaded this year ");

videos.forEach((video) => {
    let videoDate = video.uploadDate;

    if (videoDate.getMonth() == todayDate.getMonth() && videoDate.getYear() === todayDate.getYear()) {
        console.log(video.title);

    }

});



// Sorting videos by viewCount
function sortByViews(video) {



    for (let i = 0; i < video.length - 1; i++) {
        if (video[i].viewCount > video[i + 1].viewCount) {
            let temp = video[i];

            video[i] = video[i + 1];
            video[i + 1] = temp;

        }


    }
}
sortByViews(videos);



console.log("\n Sorted by Views");
videos.forEach((video) => {
    console.log(video.title+ "\n Views : "+ video.viewCount);
});


// Sorting videos by ratings
function sortByRatings(video) {

    for (let i = 0; i < video.length - 1; i++) {
        if (video[i].rating > video[i + 1].rating) {

            let temp = video[i];
            video[i] = video[i + 1];
            video[i + 1] = temp;

        }


    }
}
sortByRatings(videos);



console.log("\n Sorted by Ratings");
videos.forEach((video) => {
    console.log(video.title);
});



