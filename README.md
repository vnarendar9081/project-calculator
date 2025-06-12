# project-calculator
def calculate_project_cost():
    """
    Calculates the total estimated cost of a project based on user inputs.
    """
    print("--- Project Cost Calculator ---")
    print("Enter the following details to estimate your project's total cost.")

    total_cost = 0.0

    # Section 1: Labor Costs
    print("\n--- Labor Costs ---")
    try:
        num_roles = int(input("How many different roles/types of labor will be involved? "))
        if num_roles < 0:
            print("Number of roles cannot be negative. Setting to 0.")
            num_roles = 0
    except ValueError:
        print("Invalid input for number of roles. Assuming 0 roles for labor costs.")
        num_roles = 0

    for i in range(num_roles):
        print(f"\n--- Role {i + 1} ---")
        role_name = input(f"Enter name for Role {i + 1} (e.g., 'Developer', 'Designer'): ")
        while True:
            try:
                hourly_rate = float(input(f"Enter hourly rate for {role_name} (e.g., 50.00): $"))
                if hourly_rate < 0:
