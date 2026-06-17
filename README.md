# Advanced Student Grade Management System

A comprehensive, browser-based student grade management system with no login required. Built with HTML, CSS, and vanilla JavaScript, it uses local browser storage for data persistence.

## 🎯 Features

### Core Functionality
- **Add Student Records** - Register students with name, ID, and department
- **Semester-based Course Management** - Organize courses by semester
- **GPA Calculation** - Automatic GPA calculation using weighted grade points
- **Semester-wise GPA** - Track GPA for each semester independently
- **CGPA Tracking** - Real-time cumulative GPA across all semesters
- **Transcript Generation** - Professional university transcripts with semester breakdown
- **Search Functionality** - Filter students by name or ID
- **Edit Capabilities** - Edit student info, course details, and semester records

### Advanced Features
- ✅ **Input Validation** - Comprehensive validation for all fields
- ✅ **Duplicate Prevention** - Prevents adding the same course twice per semester
- ✅ **Delete Confirmation** - Safety modal before deleting records
- ✅ **Data Export** - Download all records as JSON for backup
- ✅ **Data Import** - Restore records from JSON backup files
- ✅ **Error Messages** - Clear, user-friendly notifications
- ✅ **Print Support** - Print transcripts directly from the browser
- ✅ **Statistics Dashboard** - Overview of overall CGPA, student count, and total courses
- ✅ **Course Editing** - Edit individual course records by semester
- ✅ **Semester Organization** - Courses grouped by semester for better tracking

## 📊 Grading Scale

| Marks | Grade | Points |
|-------|-------|--------|
| 90-100 | A | 4.0 |
| 80-89 | B | 3.0 |
| 70-79 | C | 2.0 |
| 50-69 | D | 1.0 |
| Below 50 | F | 0.0 |

## 🚀 How to Use

### Getting Started

1. **Open the Application**
   - Download the HTML file or access it through your browser
   - No installation or server setup required
   - Works offline with browser storage

2. **Add Student Information**
   - Enter Student Name (required)
   - Enter Student ID (required)
   - Enter Department (optional)
   - Enter Semester (required) - e.g., "Fall 2024", "Spring 2025"

3. **Add Course Records**
   - Select a semester for the course
   - Enter Course Name (required)
   - Enter Credit Hours (0-10)
   - Enter Marks (0-100)
   - Click "Add Record"

4. **View Student Data**
   - All students appear in the main table
   - Search by name or ID to filter results
   - See overall CGPA for each student
   - View total courses per student

5. **Edit Student Information**
   - Click "Edit" button next to a student
   - Two tabs available:
     - **Student Info**: Edit name and department
     - **Semesters**: View all semesters with courses and GPA
   - Edit individual courses or delete them
   - Each semester shows its own GPA

6. **Generate Transcripts**
   - Click "Transcript" button for any student
   - View professional formatted transcript with:
     - Student details
     - All semesters and courses
     - Semester-wise GPA
     - Overall CGPA
   - Use browser print feature for PDF export

### Data Management

#### Export Data
- Click "Export" button
- JSON file downloads automatically
- Filename: `grade-system-backup-YYYY-MM-DD.json`
- Keep as backup of your records
- Useful for data migration and security

#### Import Data
- Click "Import" button
- Select a previously exported JSON file
- System validates the file structure
- Confirm to restore all data
- Replaces existing data

#### Delete Records
- **Delete Student**: Click "Delete" button, confirm in modal
- **Delete Course**: Open student editor → semester tab → delete course
- Both require confirmation
- Record is permanently removed

## 🎓 Calculation Methods

### Semester GPA Calculation
```
Semester GPA = (Sum of (Grade Point × Credit Hours)) / (Sum of Credit Hours)
```

**Example (Fall 2024):**
- Math: Grade A (4.0) × 4 credits = 16.0
- Physics: Grade B (3.0) × 3 credits = 9.0
- English: Grade C (2.0) × 2 credits = 4.0
- Total: (16.0 + 9.0 + 4.0) / (4 + 3 + 2) = 29.0 / 9 = **3.22 GPA**

### CGPA (Cumulative GPA) Calculation
```
CGPA = (Sum of all (Grade Point × Credit Hours)) / (Sum of all Credit Hours)
```
Averages all semester GPAs weighted by credits

## 💾 Data Storage

- **Storage Method**: Browser's LocalStorage API
- **Data Format**: JSON
- **Persistence**: Data persists until browser cache is cleared
- **Backup**: Use Export feature regularly to backup data
- **Capacity**: Can store hundreds of student records

### Data Structure
```json
[
  {
    "name": "John Doe",
    "sid": "STU001",
    "dept": "Computer Science",
    "semesters": {
      "Fall 2024": [
        {
          "course": "Data Structures",
          "credit": 3,
          "marks": 85,
          "grade": "B",
          "point": 3.0
        },
        {
          "course": "Algorithms",
          "credit": 4,
          "marks": 92,
          "grade": "A",
          "point": 4.0
        }
      ],
      "Spring 2025": [
        {
          "course": "Database Systems",
          "credit": 3,
          "marks": 88,
          "grade": "B",
          "point": 3.0
        }
      ]
    }
  }
]
```

## 🔍 Input Validation

The system validates:
- ✓ Student name is not empty
- ✓ Student ID is not empty
- ✓ Course name is not empty
- ✓ Semester is selected/entered
- ✓ Credit hours are between 0-10
- ✓ Marks are between 0-100
- ✓ No duplicate courses in the same semester
- ✓ Imported JSON has valid structure

## 🌐 Browser Compatibility

Works on all modern browsers that support:
- LocalStorage API
- ES6+ JavaScript
- CSS Flexbox
- HTML5

**Tested on:**
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

## 📝 Tips & Best Practices

1. **Semester Naming**
   - Use consistent format: "Fall 2024", "Spring 2025", "Summer 2025"
   - Makes transcript organization clearer
   - Helps with sorting and searching

2. **Regular Backups**
   - Export data monthly using the Export button
   - Store backups in a safe location
   - Keep multiple backup versions

3. **Data Entry**
   - Use consistent student ID format (e.g., STU001, STU002)
   - Include semester information for tracking
   - Enter marks as whole numbers (0-100)
   - Use clear, standard course names

4. **Credit Hours**
   - Typically range from 1-4 per course
   - Total credits per semester varies by student workload
   - Used in GPA calculation with weighted average

5. **Printing**
   - Use "Print Transcript" button for official documents
   - Ensure your printer has sufficient paper
   - Save as PDF for digital records using Ctrl+P or Cmd+P

## 🆘 Troubleshooting

### Data Lost After Browser Clear
- **Solution**: Import from your backup JSON file using the Import button
- **Prevention**: Export data regularly (weekly or monthly)

### Search Not Working
- **Solution**: Ensure you're typing the exact name or ID
- **Note**: Search is case-insensitive but requires substring match

### Duplicate Course Error
- **Solution**: Check that course name matches exactly (case-insensitive)
- **Note**: Each course can only be added once per semester per student

### Marks Not Updating
- **Solution**: Close editor and reopen to see changes
- **Note**: Click Save after making edits in the student editor

### Import Fails
- **Solution**: Ensure the JSON file is from an export
- **Check**: Verify file contains valid student data structure with semesters

### Semester GPA Shows 0.00
- **Possible Cause**: All courses in that semester might have been deleted
- **Solution**: Delete empty semester or add courses to it

## 📊 Statistics Dashboard

The dashboard displays (at the top):
- **Overall CGPA** - Average CGPA of all students
- **Total Students** - Count of all registered students
- **Total Courses** - Sum of all course records across all semesters

## 🔒 Privacy & Security

- All data stored locally in your browser
- No data sent to any server
- No account creation required
- No personal information collected externally
- Data encrypted only in browser's LocalStorage

## 📄 Transcript Format

Generated transcripts include:
- Student name, ID, and department
- Organized by semester
- For each semester:
  - All courses with marks and grades
  - Semester GPA
- Overall cumulative GPA
- Generation timestamp for verification

Example transcript layout:
```
======================================================================
UNIVERSITY TRANSCRIPT
======================================================================

Name:           John Doe
Student ID:     STU001
Department:     Computer Science

======================================================================
FALL 2024
----------------------------------------------------------------------
Data Structures              | 3      | 85    | B
Algorithms                   | 4      | 92    | A
Semester GPA: 3.57

SPRING 2025
----------------------------------------------------------------------
Database Systems             | 3      | 88    | B
Web Development              | 3      | 90    | A
Semester GPA: 3.67

======================================================================
CUMULATIVE GPA: 3.62
======================================================================
```

## 🎯 Future Enhancements

Potential features for future versions:
- Dark mode theme toggle
- Statistics dashboard with charts
- Multiple grading scale options (4.0, 5.0, etc.)
- Class average analytics
- Grade distribution visualization
- Mobile responsive improvements
- Cloud storage integration
- Student performance predictions

## 💡 Contributing

Found a bug or have a suggestion? 
- Report issues on GitHub
- Submit pull requests with improvements
- Share feedback for new features

## 📧 Support

For questions or issues:
1. Check the Troubleshooting section
2. Review the How to Use section
3. Export your data as backup before major changes
4. Verify browser compatibility

## 📄 License

This project is open source and available for educational use.

---

**Version**: 3.0 (Semester-wise GPA Tracking)  
**Last Updated**: June 2026  
**Created by**: Omer Jemal

### Recent Updates
- ✅ Added semester-wise GPA tracking
- ✅ Restructured data with semester organization
- ✅ Enhanced student editor with tabs
- ✅ Improved transcript formatting
- ✅ Added course editing by semester

For the latest version and updates, visit: [GitHub Repository](https://github.com/omerjemal250/Grade-system-)
