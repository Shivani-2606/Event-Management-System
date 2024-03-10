class EventManagementSystem : JFrame() {
    // UI components
    private val eventNameField: JTextField
    private val createEventButton: JButton

    init {
        setTitle("Event Management System")
        setSize(400, 200)
        setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE)
        setLayout(java.awt.GridLayout(2, 2))
        eventNameField = JTextField()
        createEventButton = JButton("Create Event")
        add(JLabel("Event Name:"))
        add(eventNameField)
        add(JLabel()) // Placeholder for empty grid cell
        add(createEventButton)
        createEventButton.addActionListener(object : java.awt.event.ActionListener() {
            override fun actionPerformed(e: ActionEvent) {
                val eventName: String = eventNameField.getText()
                if (eventName.isEmpty()) {
                    JOptionPane.showMessageDialog(
                        this@EventManagementSystem,
                        "Please enter event name"
                    )
                } else {
                    // Call method to save event to database
                    saveEventToDatabase(eventName)
                    JOptionPane.showMessageDialog(
                        this@EventManagementSystem,
                        "Event created successfully"
                    )
                }
            }
        })
    }

    private fun saveEventToDatabase(eventName: String) {
        // Code to save event to database
        // You can use JDBC or any ORM framework for database operations
    }

    companion object {
        @JvmStatic
        fun main(args: Array<String>) {
            val ems = EventManagementSystem()
            ems.setVisible(true)
        }
    }
}
