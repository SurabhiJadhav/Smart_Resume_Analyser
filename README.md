# Smart_Resume_Analyser
This application empowers job seekers to better understand the skills they need and how to acquire them, while also providing employers with valuable insights into a candidate's abilities, talents, and experiences. With this tool, we can all work towards achieving our professional goals and unlocking our full potential.


## Background
Unemployment rates have skyrocketed in recent years. Nowadays there are thousands of people are unemployed or they are finding the jobs. Your resume communicates your qualifications and your brand—who you are and what makes you different—to employers and recruiters. In a tough job market, you need a resume that helps you stand out in a sea of applicants. Ultimately, the purpose of a strategically targeted, polished resume is to get you an interview. 
Student Employment Services is excited to help you craft an outstanding resume. To accomplish this, you must consider targeting, the resume format, and its content.
There are several reasons behind unemployment, including no proper resume, inability to find and apply for the right job, no up-to-date skills required for the job and so on.
A resume conveys to companies what you can potentially contribute to a business operation in addition to listing your skills and detailing your expertise.
To improve once resume or CVs this application can make it easier to understand what skill are needed and from where can we get it. Employers can utilise resumes to learn 
more about a candidate's abilities, talents and experiences. We are using the core concepts of Natural Language Processing for analysing the resume. This is just first step for implementing Artificial Intelligence in the field of Job Recruitment sector. 

## Objective
In current situation there are thousands of unemployed people finding the job but they are can’t able to select in the companies, the reason is they don’t know the trend of current technology & fields. May be they are lacking with the skills of resume writing. It is chances that they didn’t have done any particular certifications in particular field. So our ideas is to implement Artificial Intelligence in this field. 
AI Technology is playing a very vital role in changing our life in many ways. There are many sectors which benefited after implementing AI technology in it. 
Now it’s time for evolution in very field. With the use of Artificial Intelligence every field is growing widely. With this project our aim is to use AI in job sectors. 
This system can be use by any fresher, graduate or experienced people. Our future aim to create same module for companies oriented also, so with this application companies can directly shortlist the people using AI. We are using the core concepts of Natural Language Processing for analyzing the resume. This is just first step for implementing Artificial Intelligence in the field of Job Recruitment sector.

## Application
In our application, it is built for the any user. It is freely available to utilized. 
Anyone who wants to analyze their skill and want to understand how to make their skill stong ad where can the get them. 
This application doesn’t have any monetary service to take the charges according to the usage, any user can access this application in freely. Every user can access 
this application.

### Requirement and Analysis:
Selection of the Software with Justification: -
    ̶  Python programming language
    ̶  PyCharm IDE
    ̶  Streamlit
    ̶  NLTK
    ̶  XAMP
    ̶  GitHub 

#### Tools & Technologies: -

🔹 NLTK & Pyparser for NLP:
NLTK can be used for:
  ̶  Find text to analyse
  ̶  Pre-process your text for analysis
  ̶  Analyses your text
  ̶  Create visualizations based on your analysis
  
🔹 Streamlit for Backend:
Streamlit is special framework for handling the Data intensive 
applications, we are using it because it’s have amazing UI components, we 
don’t need to implement HTML+ CSS, everything will be handled by 
python code. It is very easy to use. In this deployment is also very easy.

🔹 PDFMiner for extracting PDF
PDFMiner, a Python library, to extract text from PDF files and perform 
text analysis.
PDFMiner attempts to reconstruct some of those structures by using 
heuristics on the positioning of characters. This works well for sentences 
and paragraphs because meaningful groups of nearby characters can be 
made.

🔹 Base64 for PDF displaying
Sometimes you have to send or output a PDF file within a text document 
(for example, HTML, JSON, XML), but you cannot do this because binary 
characters will damage the syntax of the text document. To prevent this, 
for example, you can encode PDF file to Base64 and embed it using the 
data URI.

🔹 Pillow:
Pillow also allows us to convert an image to a NumPy array. After converting 
an image to NumPy array we can read it in using PIL.

🔹 Numpy:
NumPy aims to provide an array object that is up to 50x faster than 
traditional Python lists.

🔹 Pycharm IDE:
PyCharm is professional IDE which is developed by JetBrains. The 
features which are offered by PyCharm Community version is Intelligent 
Python editor, Code debugger, Code inspection, VCS support and many 
more related to the User Interface. 

🔹 BS4 and requests for Web Scraping:
Using Beautiful Soup, you will have no problem scraping information from web 
pages. By layering Pythonic idioms on top of HTML or XML parsers, iterator,
search, and modification functions can be performed.

🔹 XAMP
It is open source control panel which is easy to use and maintain the 
apache, database, and PhpMyAdmin. It is very easy to operate. We can 
operate apache, MySQL easily from it. It is easily available for windows 
& windows & another platform

## Algorithms Design
STEP 1: GO TO SYSTEMS HOME PAGE

STEP 2: ASK USER TO UPLOAD THE RESUME.

STEP 3: IF IN PDF FORMAT THE GO FORWARD. 
ELSE THROUGH AN ERROR AND GO TO STEP 2

STEP 4: STORE IT IN SYSTEM.

STEP 5: PROCESS RESUME USING PDF2TEXT

STEP 6: PERFORM NLP PROCESSING

STEP 7: FETCH THE USER INFORMATION

STEP 8: PASS SKILL RECOMMENDATION. GENERATE SKILL 
RECOMMENDATIONS BASED ON USER’S SKILLS.

STEP 9: STORE USER DATA.

STEP 10: END 

![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/15f45772-de10-4266-a05e-4dd5aae35715)

## Security Issues 
◾ We have user and Adim login.
◾ Web application security refers to a variety of processes, technologies, or methods 
for protecting web servers, web applications, and web services such as APIs from 
attack by Internet-based threats

## ⭐PDF Extracting Code
This code is used for the PDF extraction; it will extract the Pdf of resume which is uploaded by the user.

    # def pdf_reader(file):
        resource_manager = PDFResourceManager()
        fake_file_handle = io.StringIO()
        converter = TextConverter(resource_manager, fake_file_handle, laparams=LAParams())
        page_interpreter = PDFPageInterpreter(resource_manager, converter)
        with open(file, 'rb') as fh:
            for page in PDFPage.get_pages(fh,
                                            caching=True,
                                            check_extractable=True):
                page_interpreter.process_page(page)
                print(page)
            text = fake_file_handle.getvalue()
    
        # close open handles
        converter.close()
        fake_file_handle.close()
        return text

## ⭐ Recommender Code
This code is used for the course recommender, it will fetch the user’s skills, based on that skills it will give the recommendations.

    # def course_recommender(course_list):
        st.subheader("**Courses & Certificates🎓 Recommendations**")
        rec_course = []
        no_of_reco = st.slider('Choose Number of Course Recommendations:', 1, 10, 4)
        random.shuffle(course_list)
        for c_name, c_link in course_list:
            c += 1
            st.markdown(f"({c}) [{c_name}]({c_link})")
            rec_course.append(c_name)
            if c == no_of_reco:
                break
        return rec_course

## ⭐ PDF Showing Code
This code is used to show the uploaded resume in the user interface, it simply allows to display the uploaded resume into the system.

    # def show_pdf(file_path):
        with open(file_path, "rb") as f:
            base64_pdf = base64.b64encode(f.read()).decode('utf-8')
        # pdf_display = f'<embed src="data:application/pdf;base64,{base64_pdf}" width="700" height="1000" type="application/pdf">'
        pdf_display = F'<iframe src="data:application/pdf;base64,{base64_pdf}" width="700" height="1000" type="application/pdf"></iframe>'
        st.markdown(pdf_display, unsafe_allow_html=True)

## ⭐ Insert user’s Data Code
This code is used to insert the user data into our database.

    # Definsert_data(name,email,mobile,timestamp,no_of_pages,reco_field,cand_level,skills,recommended_skills,courses):
        DB_table_name = 'user_data'
        insert_sql = "insert into " + DB_table_name + """
        values (0,%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)"""
        rec_values = (name, email, str(mobile), timestamp,str(no_of_pages), reco_field, cand_level, skills,recommended_skills,courses)
        cursor.execute(insert_sql, rec_values)
        connection.commit()

## ⭐ Visualization Code (Pie Chart)
This code is used display the Pie Chart for data analytics.

    # labels = plot_data.Predicted_Field.unique()
    values = plot_data.Predicted_Field.value_counts()
    st.subheader("**Pie-Chart📈 for Predicted Field Recommendations**")
    fig = px.pie(df, values=values, names=labels, title='Predicted Field according to the Skills')
    st.plotly_chart(fig)


#### Home page of System: -
This will be main page of our web application, user just need to visit the URL. It is just one-page application, user doesn’t need to do any Registration process. Everyone can use it directly. 
Screenshot: - 1 Homepage

#### User Role Selection: -
User can select the role from the left panel. There is 2 roles given. One is normal user another one is Admin role. In admin role, credentials are required.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/a0f5dbcb-c994-4d27-a592-39e0e9282751)

Screenshot: - 2 User role selection

#### Resume Uploader: - 
In normal user, it’s have the facility to upload the resume. User can upload the PDF by click on browse button or by just drag & drop. Currently PDF format is only supported.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/5c61fd7a-853b-4867-b97e-7e0fda7fc805)

Screenshot: - 3 Resume Uploader

#### Resume Display: -
After the uploading the resume, it will take time to upload the resume, after successfully completion it will show the uploaded resume into our application.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/1d5fb942-5ef2-42ee-940f-4e77517576a7)

Screenshot: - 3 Resume Uploader

#### User Information: - 
Our system will fetch the user’s information from the resume, it will display this information into our application. It will predict the user at intermediate level or fresher or experienced. 
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/72523877-41ea-41b8-aeb5-ae18883fa820)

Screenshot: - 5 User Information

#### Skills & Career Recommendations: -
Our system will fetch the user’s skills from the resume, and it will give the career recommendations based on the skills that you have. 
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/d44c2ca9-9544-4a97-a6bc-5f1a9b8ad519)

Screenshot: - 6 Skills & Career Recommendations

#### Courses Recommendations: -
Our System will show the courses recommendations based on the user’s skills. All the courses & certifications are combinations of free and paid. User can see 1-10 courses from the recommendations. User can scale the courses and they can navigate to course by just clicking on them.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/5e2435e8-9229-4b7e-9c24-76ada3fa9a3b)

Screenshot: - 7 Courses Recommendations

#### Resume writing Tips & Tricks: -
Our system will give you the topics recommendations which you can add into the resume, like declarations, hobbies, achievements or objective, it will suggest to you add if you haven’t added then
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/40d2efd4-0ec6-468d-9987-7ec564a9acdb)

Screenshot: - 8 Resume writing Tips & Tricks

#### Resume Score: -
Our system will generate the score of the user from the uploaded resume.
 ![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/e3354b24-cc08-451d-bc04-f3c097e8e40f)

 Screenshot: - 9 Resume Score

#### Admin side: -
In selection panel, if you will select admin side, then it will show you the Admin Login panel. With default credentials admin login.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/c4fc87a9-fe11-45a4-ac9a-47eb047b05b9)

 Screenshot: - 12 Admin’s side

#### Admin Side User report: -
Admin can see the user’s data which is collected from the user’s resume.
![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/4b6183b7-a154-42f1-b728-311ec35023a6)

Screenshot: - 13 Admin Side User report

#### Admin Side Visualizations: -
Our system will display the visualizations based on the data. It is Pie-Chart for predicted field recommendations. Next screenshot chart is for 
 ![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/6215e0ff-ac4d-4516-851b-a7bdf96cfc32)
 Screenshot: - 14 Admin Side Visualizations
 
 ![image](https://github.com/SurabhiJadhav/Smart_Resume_Analyser/assets/130740664/82f40271-8158-4f70-aa5f-1a798e57e359)

 Screenshot: - 15 Admin Side Visualizations

