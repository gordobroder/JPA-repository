package com.example.demo;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.context.ApplicationListener;
import org.springframework.context.event.ContextRefreshedEvent;
import org.springframework.stereotype.Component;

import com.example.demo.entity.Role;
import com.example.demo.entity.User;
import com.example.demo.repository.RoleRepository;
import com.example.demo.repository.UserRepository;

@Component
public class Initializer implements ApplicationListener<ContextRefreshedEvent> {
	
	@Autowired
	private RoleRepository roleRepository;
	
	@Autowired
	private UserRepository userRepository;
	
	
	@Override
	public void onApplicationEvent(ContextRefreshedEvent event) {
		
		Role role = new Role();
		
		role.setName("Admin");
		role.setStatus(StatusRole.ATIVO);
		
		Role role2 = new Role();
		
		role2.setName("Aluno");
		role2.setStatus(StatusRole.INATIVO);
		
		this.roleRepository.save(role);
		this.roleRepository.save(role2);
		
		User user = new User();
		
		user.setName("Gustavo");
		user.setEmail("gustavo@gmail.com");
		user.setRole(role);
		
		User user2 = new User();
		
		user2.setName("Gordo");
		user2.setEmail("gordo@gmail.com");
		user2.setRole(role);
				
		this.userRepository.save(user);
		this.userRepository.save(user2);
		
	}

}
